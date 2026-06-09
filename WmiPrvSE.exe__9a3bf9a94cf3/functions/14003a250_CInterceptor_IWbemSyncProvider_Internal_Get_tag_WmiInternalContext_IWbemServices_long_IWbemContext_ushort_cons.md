# CInterceptor_IWbemSyncProvider::Internal_Get(_tag_WmiInternalContext,IWbemServices *,long,IWbemContext *,ushort const *,ushort const *,IWbemObjectSink *)

- ea: `0x14003a250`
- end: `0x14003a353`
- name: `?Internal_Get@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@PEAUIWbemServices@@JPEAUIWbemContext@@PEBG3PEAUIWbemObjectSink@@@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140021434`
- `0x14002145c`
- `0x1400234b8`
- `0x14003a250`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003a300`
- `wbemcomn!GetMemLogObject` at `0x14003a300`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003a30b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003a30b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_Get(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int128 v8; // xmm0
  int v12; // ebx
  __int64 v13; // rcx
  CMemoryLog *MemLogObject; // rax
  struct IServerSecurity *v16; // [rsp+40h] [rbp-48h] BYREF
  struct IUnknown *v17; // [rsp+48h] [rbp-40h] BYREF
  __int128 v18; // [rsp+50h] [rbp-38h] BYREF
  int v19; // [rsp+98h] [rbp+10h] BYREF

  v8 = *a2;
  v19 = 0;
  v17 = 0;
  v16 = 0;
  v18 = v8;
  v12 = ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost((void **)&v18, &v19, &v17, &v16);
  if ( v12 < 0
    || (v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)(a1 - 8) + 24LL))(
                a1 - 8,
                a3,
                a4,
                a5,
                a6,
                a7,
                a8),
        ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(v13, &v17, &v16, &v19),
        v12 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003a250  mov     rax, rsp
0x14003a253  push    rbx
0x14003a254  push    rbp
0x14003a255  push    rsi
0x14003a256  push    rdi
0x14003a257  sub     rsp, 68h
0x14003a25b  movups  xmm0, xmmword ptr [rdx]
0x14003a25e  mov     edi, r9d
0x14003a261  mov     dword ptr [rax+10h], 0
0x14003a268  mov     rsi, r8
0x14003a26b  mov     qword ptr [rax-40h], 0
0x14003a273  mov     rbp, rcx
0x14003a276  mov     qword ptr [rax-48h], 0
0x14003a27e  lea     r9, [rax-48h]
0x14003a282  lea     r8, [rax-40h]
0x14003a286  lea     rdx, [rax+10h]
0x14003a28a  lea     rcx, [rax-38h]
0x14003a28e  movdqu  xmmword ptr [rax-38h], xmm0
0x14003a293  call    ?Begin_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@@Z; ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(_tag_WmiInternalContext,int &,IUnknown * &,IServerSecurity * &)
0x14003a298  mov     ebx, eax
0x14003a29a  test    eax, eax
0x14003a29c  js      short loc_14003A300
0x14003a29e  mov     rdx, [rsp+88h+arg_38]
0x14003a2a6  lea     rcx, [rbp-8]
0x14003a2aa  mov     rax, [rcx]
0x14003a2ad  mov     r8d, edi
0x14003a2b0  mov     r9, [rsp+88h+arg_20]
0x14003a2b8  mov     [rsp+88h+var_58], rdx
0x14003a2bd  mov     rdx, [rsp+88h+arg_30]
0x14003a2c5  mov     rax, [rax+18h]
0x14003a2c9  mov     [rsp+88h+var_60], rdx
0x14003a2ce  mov     rdx, [rsp+88h+arg_28]
0x14003a2d6  mov     [rsp+88h+var_68], rdx
0x14003a2db  mov     rdx, rsi
0x14003a2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a2e3  lea     r9, [rsp+88h+arg_8]
0x14003a2eb  mov     ebx, eax
0x14003a2ed  lea     r8, [rsp+88h+var_48]
0x14003a2f2  lea     rdx, [rsp+88h+var_40]
0x14003a2f7  call    ?End_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(_tag_WmiInternalContext,IUnknown * &,IServerSecurity * &,int &)
0x14003a2fc  test    ebx, ebx
0x14003a2fe  jns     short loc_14003A311
0x14003a300  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003a306  mov     rcx, rax
0x14003a309  mov     edx, ebx
0x14003a30b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003a311  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a318  lea     rax, WPP_GLOBAL_Control
0x14003a31f  cmp     rcx, rax
0x14003a322  jz      short loc_14003A348
0x14003a324  test    byte ptr [rcx+1Ch], 4
0x14003a328  jz      short loc_14003A348
0x14003a32a  cmp     byte ptr [rcx+19h], 2
0x14003a32e  jb      short loc_14003A348
0x14003a330  mov     rcx, [rcx+10h]
0x14003a334  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003a33b  mov     edx, 3Eh ; '>'
0x14003a340  mov     r9d, ebx
0x14003a343  call    WPP_SF_d
0x14003a348  mov     eax, ebx
0x14003a34a  add     rsp, 68h
0x14003a34e  pop     rdi
0x14003a34f  pop     rsi
0x14003a350  pop     rbp
0x14003a351  pop     rbx
0x14003a352  retn
```
