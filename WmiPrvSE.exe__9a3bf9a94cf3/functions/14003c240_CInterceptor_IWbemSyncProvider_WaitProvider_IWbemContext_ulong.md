# CInterceptor_IWbemSyncProvider::WaitProvider(IWbemContext *,ulong)

- ea: `0x14003c240`
- end: `0x14003c384`
- name: `?WaitProvider@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemContext@@K@Z`
- size: `324`
- prototype: `int(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemContext *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030478`
- `0x14003c240`
- `0x1400419ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c2d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c31f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c2d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003c31f`
- `wbemcomn!GetMemLogObject` at `0x14003c2e2`
- `wbemcomn!GetMemLogObject` at `0x14003c333`
- `wbemcomn!GetMemLogObject` at `0x14003c2e2`
- `wbemcomn!GetMemLogObject` at `0x14003c333`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c2f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c33e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c2f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003c33e`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::WaitProvider(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemContext *a2,
        DWORD a3)
{
  _BYTE *v6; // rcx
  struct IWbemContext *v7; // rcx
  unsigned int v8; // ebx
  void *v9; // rcx
  CMemoryLog *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+60h] [rbp+8h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, a2, a3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 98) )
  {
    v8 = 0;
LABEL_18:
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[28] & 4) == 0 || v6[25] < 2u )
      return v8;
    v11 = 179;
    v12 = v8;
    goto LABEL_22;
  }
  v7 = (struct IWbemContext *)*((_QWORD *)this + 51);
  v15 = 0;
  v8 = ProviderSubSystem_Common_Globals::IsDependantCall(v7, a2, &v15);
  if ( (v8 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
    goto LABEL_16;
  }
  v9 = (void *)*((_QWORD *)this + 50);
  if ( v15 )
  {
    if ( WaitForSingleObject(v9, 0) == 258 )
      return 1;
    goto LABEL_16;
  }
  if ( WaitForSingleObject(v9, a3) != 258 )
  {
LABEL_16:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v10 = GetMemLogObject();
  v8 = -2147217389;
  CMemoryLog::Write(v10, -2147217389);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return v8;
  }
  v11 = 178;
  v12 = 2147749907LL;
LABEL_22:
  WPP_SF_d(*((_QWORD *)v6 + 2), v11, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v12);
  return v8;
}

```

## disassembly

```asm
0x14003c240  push    rbx
0x14003c242  push    rsi
0x14003c243  push    rdi
0x14003c244  push    r15
0x14003c246  sub     rsp, 38h
0x14003c24a  mov     esi, r8d
0x14003c24d  mov     rbx, rdx
0x14003c250  mov     rdi, rcx
0x14003c253  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c25a  lea     r15, WPP_GLOBAL_Control
0x14003c261  cmp     rcx, r15
0x14003c264  jz      short loc_14003C296
0x14003c266  test    byte ptr [rcx+1Ch], 4
0x14003c26a  jz      short loc_14003C296
0x14003c26c  cmp     byte ptr [rcx+19h], 5
0x14003c270  jb      short loc_14003C296
0x14003c272  mov     rcx, [rcx+10h]
0x14003c276  mov     edx, 0B1h
0x14003c27b  mov     [rsp+58h+var_38], r8d
0x14003c280  mov     r9, rbx
0x14003c283  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003c28a  call    WPP_SF_qd
0x14003c28f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c296  cmp     dword ptr [rdi+188h], 0
0x14003c29d  jnz     loc_14003C34D
0x14003c2a3  mov     rcx, [rdi+198h]; struct IWbemContext *
0x14003c2aa  lea     r8, [rsp+58h+arg_0]; int *
0x14003c2af  mov     rdx, rbx; struct IWbemContext *
0x14003c2b2  mov     [rsp+58h+arg_0], 0
0x14003c2ba  call    ?IsDependantCall@ProviderSubSystem_Common_Globals@@SAJPEAUIWbemContext@@0AEAH@Z; ProviderSubSystem_Common_Globals::IsDependantCall(IWbemContext *,IWbemContext *,int &)
0x14003c2bf  mov     ebx, eax
0x14003c2c1  test    eax, eax
0x14003c2c3  js      short loc_14003C333
0x14003c2c5  cmp     [rsp+58h+arg_0], 0
0x14003c2ca  mov     rcx, [rdi+190h]; hHandle
0x14003c2d1  jnz     short loc_14003C31D
0x14003c2d3  mov     edx, esi; dwMilliseconds
0x14003c2d5  call    cs:__imp_WaitForSingleObject
0x14003c2db  cmp     eax, 102h
0x14003c2e0  jnz     short loc_14003C344
0x14003c2e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003c2e8  mov     ebx, 80041013h
0x14003c2ed  mov     rcx, rax
0x14003c2f0  mov     edx, ebx
0x14003c2f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003c2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c2ff  cmp     rcx, r15
0x14003c302  jz      short loc_14003C378
0x14003c304  test    byte ptr [rcx+1Ch], 4
0x14003c308  jz      short loc_14003C378
0x14003c30a  cmp     byte ptr [rcx+19h], 2
0x14003c30e  jb      short loc_14003C378
0x14003c310  mov     edx, 0B2h
0x14003c315  mov     r9d, 80041013h
0x14003c31b  jmp     short loc_14003C368
0x14003c31d  xor     edx, edx; dwMilliseconds
0x14003c31f  call    cs:__imp_WaitForSingleObject
0x14003c325  cmp     eax, 102h
0x14003c32a  jnz     short loc_14003C344
0x14003c32c  mov     eax, 1
0x14003c331  jmp     short loc_14003C37A
0x14003c333  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003c339  mov     rcx, rax
0x14003c33c  mov     edx, ebx
0x14003c33e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003c344  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c34b  jmp     short loc_14003C34F
0x14003c34d  xor     ebx, ebx
0x14003c34f  cmp     rcx, r15
0x14003c352  jz      short loc_14003C378
0x14003c354  test    byte ptr [rcx+1Ch], 4
0x14003c358  jz      short loc_14003C378
0x14003c35a  cmp     byte ptr [rcx+19h], 2
0x14003c35e  jb      short loc_14003C378
0x14003c360  mov     edx, 0B3h
0x14003c365  mov     r9d, ebx
0x14003c368  mov     rcx, [rcx+10h]
0x14003c36c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003c373  call    WPP_SF_d
0x14003c378  mov     eax, ebx
0x14003c37a  add     rsp, 38h
0x14003c37e  pop     r15
0x14003c380  pop     rdi
0x14003c381  pop     rsi
0x14003c382  pop     rbx
0x14003c383  retn
```
