# JobExecution::CompleteBITSJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000a14c`
- end: `0x14000a229`
- name: `?CompleteBITSJob@JobExecution@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000d134`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x14000904c`
- `0x14000a14c`
- `0x140015464`
- `0x14001a8d0`
- `0x14001c010`

## string_xrefs

- `0x14000a1da`: `Successfully completed BITS job %1.`
- `0x14000a1f8`: `Failed to complete BITS job %1 . Error 0x%2!x!`

## pseudocode

```c
__int64 __fastcall JobExecution::CompleteBITSJob(_QWORD *a1)
{
  _QWORD *v1; // rbx
  int v2; // edi
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  struct _GUID v5; // [rsp+28h] [rbp-20h] BYREF

  v1 = a1;
  v5 = 0;
  v4 = 0;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  v2 = ConvertStringToGuid((const unsigned __int16 *)a1, &v5);
  if ( v2 < 0
    || (v2 = ((__int64 (__fastcall *)(struct IBackgroundCopyManager *, struct _GUID *, __int64 *))JobExecution::copyManager->lpVtbl->GetJobA)(
               JobExecution::copyManager,
               &v5,
               &v4),
        v2 < 0)
    || (v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4), v2 < 0) )
  {
    if ( v1[3] >= 8u )
      v1 = (_QWORD *)*v1;
    LogError(L"Failed to complete BITS job %1 . Error 0x%2!x!", v1, (unsigned int)v2);
  }
  else
  {
    if ( v1[3] >= 8u )
      v1 = (_QWORD *)*v1;
    LogInfo(L"Successfully completed BITS job %1.", v1);
  }
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000a14c  mov     [rsp+arg_8], rbx
0x14000a151  push    rdi
0x14000a152  sub     rsp, 40h
0x14000a156  mov     rax, cs:__security_cookie
0x14000a15d  xor     rax, rsp
0x14000a160  mov     [rsp+48h+var_10], rax
0x14000a165  mov     rbx, rcx
0x14000a168  xorps   xmm0, xmm0
0x14000a16b  movups  xmmword ptr [rsp+48h+var_20.Data1], xmm0
0x14000a170  mov     [rsp+48h+var_28], 0
0x14000a179  cmp     qword ptr [rcx+18h], 8
0x14000a17e  jb      short loc_14000A183
0x14000a180  mov     rcx, [rcx]; unsigned __int16 *
0x14000a183  lea     rdx, [rsp+48h+var_20]; struct _GUID *
0x14000a188  call    ?ConvertStringToGuid@@YAJPEBGPEAU_GUID@@@Z; ConvertStringToGuid(ushort const *,_GUID *)
0x14000a18d  mov     edi, eax
0x14000a18f  test    eax, eax
0x14000a191  js      short loc_14000A1E8
0x14000a193  mov     rcx, cs:?copyManager@JobExecution@@0V?$CComPtr@UIBackgroundCopyManager@@@ATL@@A; ATL::CComPtr<IBackgroundCopyManager> JobExecution::copyManager
0x14000a19a  mov     rax, [rcx]
0x14000a19d  lea     r8, [rsp+48h+var_28]
0x14000a1a2  lea     rdx, [rsp+48h+var_20]
0x14000a1a7  mov     rax, [rax+20h]
0x14000a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1b0  mov     edi, eax
0x14000a1b2  test    eax, eax
0x14000a1b4  js      short loc_14000A1E8
0x14000a1b6  mov     rcx, [rsp+48h+var_28]
0x14000a1bb  mov     rax, [rcx]
0x14000a1be  mov     rax, [rax+48h]
0x14000a1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1c7  mov     edi, eax
0x14000a1c9  test    eax, eax
0x14000a1cb  js      short loc_14000A1E8
0x14000a1cd  cmp     qword ptr [rbx+18h], 8
0x14000a1d2  jb      short loc_14000A1D7
0x14000a1d4  mov     rbx, [rbx]
0x14000a1d7  mov     rdx, rbx
0x14000a1da  lea     rcx, aSuccessfullyCo; "Successfully completed BITS job %1."
0x14000a1e1  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000a1e6  jmp     short loc_14000A205
0x14000a1e8  cmp     qword ptr [rbx+18h], 8
0x14000a1ed  jb      short loc_14000A1F2
0x14000a1ef  mov     rbx, [rbx]
0x14000a1f2  mov     r8d, edi
0x14000a1f5  mov     rdx, rbx
0x14000a1f8  lea     rcx, aFailedToComple; "Failed to complete BITS job %1 . Error "...
0x14000a1ff  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000a204  nop
0x14000a205  lea     rcx, [rsp+48h+var_28]
0x14000a20a  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x14000a20f  mov     eax, edi
0x14000a211  mov     rcx, [rsp+48h+var_10]
0x14000a216  xor     rcx, rsp; StackCookie
0x14000a219  call    __security_check_cookie
0x14000a21e  mov     rbx, [rsp+48h+arg_8]
0x14000a223  add     rsp, 40h
0x14000a227  pop     rdi
0x14000a228  retn
```
