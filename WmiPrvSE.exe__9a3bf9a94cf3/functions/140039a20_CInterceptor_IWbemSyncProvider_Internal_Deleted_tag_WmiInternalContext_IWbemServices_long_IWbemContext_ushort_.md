# CInterceptor_IWbemSyncProvider::Internal_Deleted(_tag_WmiInternalContext,IWbemServices *,long,IWbemContext *,ushort const *,ushort const *,ushort const *,IWbemClassObject *)

- ea: `0x140039a20`
- end: `0x140039b30`
- name: `?Internal_Deleted@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@PEAUIWbemServices@@JPEAUIWbemContext@@PEBG33PEAUIWbemClassObject@@@Z`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140021434`
- `0x14002145c`
- `0x1400234b8`
- `0x140039a20`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140039add`
- `wbemcomn!GetMemLogObject` at `0x140039add`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039ae8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039ae8`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_Deleted(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int128 v9; // xmm0
  int v13; // ebx
  __int64 v14; // rcx
  CMemoryLog *MemLogObject; // rax
  struct IServerSecurity *v17; // [rsp+50h] [rbp-48h] BYREF
  struct IUnknown *v18; // [rsp+58h] [rbp-40h] BYREF
  __int128 v19; // [rsp+60h] [rbp-38h] BYREF
  int v20; // [rsp+A8h] [rbp+10h] BYREF

  v9 = *a2;
  v20 = 0;
  v18 = 0;
  v17 = 0;
  v19 = v9;
  v13 = ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost((void **)&v19, &v20, &v18, &v17);
  if ( v13 < 0
    || (v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64))(*(_QWORD *)(a1 - 8) + 48LL))(
                a1 - 8,
                a3,
                a4,
                a5,
                a6,
                a7,
                a8,
                a9),
        ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(v14, &v18, &v17, &v20),
        v13 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v13);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140039a20  mov     rax, rsp
0x140039a23  push    rbx
0x140039a24  push    rbp
0x140039a25  push    rsi
0x140039a26  push    rdi
0x140039a27  sub     rsp, 78h
0x140039a2b  movups  xmm0, xmmword ptr [rdx]
0x140039a2e  mov     edi, r9d
0x140039a31  mov     dword ptr [rax+10h], 0
0x140039a38  mov     rsi, r8
0x140039a3b  mov     qword ptr [rax-40h], 0
0x140039a43  mov     rbp, rcx
0x140039a46  mov     qword ptr [rax-48h], 0
0x140039a4e  lea     r9, [rax-48h]
0x140039a52  lea     r8, [rax-40h]
0x140039a56  lea     rdx, [rax+10h]
0x140039a5a  lea     rcx, [rax-38h]
0x140039a5e  movdqu  xmmword ptr [rax-38h], xmm0
0x140039a63  call    ?Begin_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@@Z; ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(_tag_WmiInternalContext,int &,IUnknown * &,IServerSecurity * &)
0x140039a68  mov     ebx, eax
0x140039a6a  test    eax, eax
0x140039a6c  js      short loc_140039ADD
0x140039a6e  mov     rdx, [rsp+98h+arg_40]
0x140039a76  lea     rcx, [rbp-8]
0x140039a7a  mov     rax, [rcx]
0x140039a7d  mov     r8d, edi
0x140039a80  mov     r9, [rsp+98h+arg_20]
0x140039a88  mov     [rsp+98h+var_60], rdx
0x140039a8d  mov     rdx, [rsp+98h+arg_38]
0x140039a95  mov     rax, [rax+30h]
0x140039a99  mov     [rsp+98h+var_68], rdx
0x140039a9e  mov     rdx, [rsp+98h+arg_30]
0x140039aa6  mov     [rsp+98h+var_70], rdx
0x140039aab  mov     rdx, [rsp+98h+arg_28]
0x140039ab3  mov     [rsp+98h+var_78], rdx
0x140039ab8  mov     rdx, rsi
0x140039abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039ac0  lea     r9, [rsp+98h+arg_8]
0x140039ac8  mov     ebx, eax
0x140039aca  lea     r8, [rsp+98h+var_48]
0x140039acf  lea     rdx, [rsp+98h+var_40]
0x140039ad4  call    ?End_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(_tag_WmiInternalContext,IUnknown * &,IServerSecurity * &,int &)
0x140039ad9  test    ebx, ebx
0x140039adb  jns     short loc_140039AEE
0x140039add  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140039ae3  mov     rcx, rax
0x140039ae6  mov     edx, ebx
0x140039ae8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140039aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140039af5  lea     rax, WPP_GLOBAL_Control
0x140039afc  cmp     rcx, rax
0x140039aff  jz      short loc_140039B25
0x140039b01  test    byte ptr [rcx+1Ch], 4
0x140039b05  jz      short loc_140039B25
0x140039b07  cmp     byte ptr [rcx+19h], 2
0x140039b0b  jb      short loc_140039B25
0x140039b0d  mov     rcx, [rcx+10h]
0x140039b11  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140039b18  mov     edx, 40h ; '@'
0x140039b1d  mov     r9d, ebx
0x140039b20  call    WPP_SF_d
0x140039b25  mov     eax, ebx
0x140039b27  add     rsp, 78h
0x140039b2b  pop     rdi
0x140039b2c  pop     rsi
0x140039b2d  pop     rbp
0x140039b2e  pop     rbx
0x140039b2f  retn
```
