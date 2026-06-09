# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x180015a1c`
- end: `0x180015a70`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800165bc`
- `0x180035eac`
- `0x18003c7a8`
- `0x180041334`
- `0x180071868`
- `0x180075bec`

## callees

- `0x180015a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a60`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rbp
  void *v5; // r14
  DWORD LastError; // ebx

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v4);
      SetLastError(LastError);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180015a1c  push    rbx
0x180015a1e  push    rbp
0x180015a1f  push    rsi
0x180015a20  push    rdi
0x180015a21  push    r14
0x180015a23  sub     rsp, 20h
0x180015a27  mov     rsi, rdx
0x180015a2a  mov     rdi, rcx
0x180015a2d  cmp     rcx, rdx
0x180015a30  jz      short loc_180015A47
0x180015a32  mov     rbp, [rcx]
0x180015a35  mov     r14, [rdx]
0x180015a38  test    rbp, rbp
0x180015a3b  jnz     short loc_180015A55
0x180015a3d  mov     [rdi], r14
0x180015a40  mov     qword ptr [rsi], 0
0x180015a47  mov     rax, rdi
0x180015a4a  add     rsp, 20h
0x180015a4e  pop     r14
0x180015a50  pop     rdi
0x180015a51  pop     rsi
0x180015a52  pop     rbp
0x180015a53  pop     rbx
0x180015a54  retn
0x180015a55  call    cs:__imp_GetLastError
0x180015a5b  mov     rcx, rbp; pv
0x180015a5e  mov     ebx, eax
0x180015a60  call    cs:__imp_CoTaskMemFree
0x180015a66  mov     ecx, ebx; dwErrCode
0x180015a68  call    cs:__imp_SetLastError
0x180015a6e  jmp     short loc_180015A3D
```
