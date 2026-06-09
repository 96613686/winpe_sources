# CInterceptor_IWbemSyncProvider::Internal_Set(_tag_WmiInternalContext,IWbemServices *,long,IWbemContext *,ushort const *,ushort const *,ushort const *,IWbemClassObject *,IWbemClassObject *)

- ea: `0x14003b0e0`
- end: `0x14003b1f5`
- name: `?Internal_Set@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@PEAUIWbemServices@@JPEAUIWbemContext@@PEBG33PEAUIWbemClassObject@@4@Z`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140021434`
- `0x14002145c`
- `0x1400234b8`
- `0x14003b0e0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003b196`
- `wbemcomn!GetMemLogObject` at `0x14003b196`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b1a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b1a1`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_Set(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int128 v10; // xmm0
  int v14; // ebx
  __int64 v15; // rcx
  CMemoryLog *MemLogObject; // rax
  struct IServerSecurity *v18; // [rsp+50h] [rbp-20h] BYREF
  struct IUnknown *v19; // [rsp+58h] [rbp-18h] BYREF
  __int128 v20; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+98h] [rbp+28h] BYREF

  v10 = *a2;
  v21 = 0;
  v19 = 0;
  v18 = 0;
  v20 = v10;
  v14 = ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost((void **)&v20, &v21, &v19, &v18);
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64, __int64))(*(_QWORD *)(a1 - 8) + 40LL))(
                a1 - 8,
                a3,
                a4,
                a5,
                a6,
                a7,
                a8,
                a9,
                a10),
        ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(v15, &v19, &v18, &v21),
        v14 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003b0e0  mov     [rsp-18h+arg_0], rbx
0x14003b0e5  mov     [rsp-18h+arg_10], rsi
0x14003b0ea  push    rbp
0x14003b0eb  push    rdi
0x14003b0ec  push    r14
0x14003b0ee  mov     rbp, rsp
0x14003b0f1  sub     rsp, 70h
0x14003b0f5  movups  xmm0, xmmword ptr [rdx]
0x14003b0f8  mov     edi, r9d
0x14003b0fb  mov     [rbp+arg_8], 0
0x14003b102  mov     rsi, r8
0x14003b105  mov     [rbp+var_18], 0
0x14003b10d  mov     r14, rcx
0x14003b110  mov     [rbp+var_20], 0
0x14003b118  lea     r9, [rbp+var_20]
0x14003b11c  lea     r8, [rbp+var_18]
0x14003b120  lea     rdx, [rbp+arg_8]
0x14003b124  lea     rcx, [rbp+var_10]
0x14003b128  movdqu  [rbp+var_10], xmm0
0x14003b12d  call    ?Begin_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@@Z; ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(_tag_WmiInternalContext,int &,IUnknown * &,IServerSecurity * &)
0x14003b132  mov     ebx, eax
0x14003b134  test    eax, eax
0x14003b136  js      short loc_14003B196
0x14003b138  mov     rdx, [rbp+arg_48]
0x14003b13c  lea     rcx, [r14-8]
0x14003b140  mov     rax, [rcx]
0x14003b143  mov     r8d, edi
0x14003b146  mov     r9, [rbp+arg_20]
0x14003b14a  mov     [rsp+70h+var_30], rdx
0x14003b14f  mov     rdx, [rbp+arg_40]
0x14003b153  mov     rax, [rax+28h]
0x14003b157  mov     [rsp+70h+var_38], rdx
0x14003b15c  mov     rdx, [rbp+arg_38]
0x14003b160  mov     [rsp+70h+var_40], rdx
0x14003b165  mov     rdx, [rbp+arg_30]
0x14003b169  mov     [rsp+70h+var_48], rdx
0x14003b16e  mov     rdx, [rbp+arg_28]
0x14003b172  mov     [rsp+70h+var_50], rdx
0x14003b177  mov     rdx, rsi
0x14003b17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b17f  lea     r9, [rbp+arg_8]
0x14003b183  mov     ebx, eax
0x14003b185  lea     r8, [rbp+var_20]
0x14003b189  lea     rdx, [rbp+var_18]
0x14003b18d  call    ?End_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(_tag_WmiInternalContext,IUnknown * &,IServerSecurity * &,int &)
0x14003b192  test    ebx, ebx
0x14003b194  jns     short loc_14003B1A7
0x14003b196  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003b19c  mov     rcx, rax
0x14003b19f  mov     edx, ebx
0x14003b1a1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003b1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1ae  lea     rax, WPP_GLOBAL_Control
0x14003b1b5  cmp     rcx, rax
0x14003b1b8  jz      short loc_14003B1DE
0x14003b1ba  test    byte ptr [rcx+1Ch], 4
0x14003b1be  jz      short loc_14003B1DE
0x14003b1c0  cmp     byte ptr [rcx+19h], 2
0x14003b1c4  jb      short loc_14003B1DE
0x14003b1c6  mov     rcx, [rcx+10h]
0x14003b1ca  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003b1d1  mov     edx, 3Fh ; '?'
0x14003b1d6  mov     r9d, ebx
0x14003b1d9  call    WPP_SF_d
0x14003b1de  lea     r11, [rsp+70h+var_s0]
0x14003b1e3  mov     eax, ebx
0x14003b1e5  mov     rbx, [r11+20h]
0x14003b1e9  mov     rsi, [r11+30h]
0x14003b1ed  mov     rsp, r11
0x14003b1f0  pop     r14
0x14003b1f2  pop     rdi
0x14003b1f3  pop     rbp
0x14003b1f4  retn
```
