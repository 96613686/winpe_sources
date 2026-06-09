# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18004f380`
- end: `0x18004f3bc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000c490`
- `0x1800261d8`
- `0x18002636c`
- `0x180038dec`
- `0x18004f010`
- `0x18004f2dc`

## callees

- `0x18004f380`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f397`
- `KERNEL32!GetLastError` at `0x18004f397`
- `KERNEL32!SetLastError` at `0x18004f3aa`
- `KERNEL32!SetLastError` at `0x18004f3aa`
- `ole32!CoTaskMemFree` at `0x18004f3a2`
- `ole32!CoTaskMemFree` at `0x18004f3a2`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18004f380  push    rbx
0x18004f382  push    rbp
0x18004f383  push    rsi
0x18004f384  push    rdi
0x18004f385  sub     rsp, 28h
0x18004f389  mov     rsi, [rcx]
0x18004f38c  mov     rbp, rdx
0x18004f38f  mov     rdi, rcx
0x18004f392  test    rsi, rsi
0x18004f395  jz      short loc_18004F3B0
0x18004f397  call    cs:__imp_GetLastError
0x18004f39d  mov     rcx, rsi; pv
0x18004f3a0  mov     ebx, eax
0x18004f3a2  call    cs:__imp_CoTaskMemFree
0x18004f3a8  mov     ecx, ebx; dwErrCode
0x18004f3aa  call    cs:__imp_SetLastError
0x18004f3b0  mov     [rdi], rbp
0x18004f3b3  add     rsp, 28h
0x18004f3b7  pop     rdi
0x18004f3b8  pop     rsi
0x18004f3b9  pop     rbp
0x18004f3ba  pop     rbx
0x18004f3bb  retn
```
