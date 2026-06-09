# Microsoft::DiagnosticsHub::UnifiedPlatform::TdhGetProperty(_EVENT_RECORD *,ulong,_TDH_CONTEXT *,ulong,_PROPERTY_DATA_DESCRIPTOR *,ulong,uchar *)

- ea: `0x180041fac`
- end: `0x1800420ea`
- name: `?TdhGetProperty@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAKPEAU_EVENT_RECORD@@KPEAU_TDH_CONTEXT@@KPEAU_PROPERTY_DATA_DESCRIPTOR@@KPEAE@Z`
- size: `318`
- prototype: `unsigned int __fastcall(Microsoft::DiagnosticsHub::UnifiedPlatform *__hidden this, struct _EVENT_RECORD *, unsigned int, struct _TDH_CONTEXT *, unsigned int, struct _PROPERTY_DATA_DESCRIPTOR *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017dc4`
- `0x180018214`

## callees

- `0x180041fac`
- `0x180049bac`
- `0x180049c18`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18004202e`
- `KERNEL32!LoadLibraryExW` at `0x18004204f`
- `KERNEL32!LoadLibraryExW` at `0x18004202e`
- `KERNEL32!LoadLibraryExW` at `0x18004204f`
- `KERNEL32!GetLastError` at `0x18004207d`
- `KERNEL32!GetLastError` at `0x18004207d`
- `KERNEL32!GetProcAddress` at `0x18004206b`
- `KERNEL32!GetProcAddress` at `0x18004206b`

## string_xrefs

- `0x180042042`: `tdh.dll`
- `0x180042012`: `api-ms-win-eventing-tdh-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::UnifiedPlatform::TdhGetProperty(
        Microsoft::DiagnosticsHub::UnifiedPlatform *this,
        struct _EVENT_RECORD *a2,
        __int64 a3,
        struct _TDH_CONTEXT *a4,
        __int64 a5,
        struct _PROPERTY_DATA_DESCRIPTOR *a6,
        __int64 a7)
{
  HMODULE Library; // rax

  if ( dword_180077AF0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180077AF0);
    if ( dword_180077AF0 == -1 )
    {
      qword_180077B04 = 0;
      dword_180077B0C = 0;
      qword_180077AF8 = 0;
      dword_180077B00 = 0;
      Library = LoadLibraryExW(L"api-ms-win-eventing-tdh-l1-1-0.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_180077B04 + 4) = (__int64)Library;
      if ( !Library
        && (Library = LoadLibraryExW(L"tdh.dll", 0, 0x800u),
            (*(__int64 *)((char *)&qword_180077B04 + 4) = (__int64)Library) == 0)
        || (qword_180077AF8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))GetProcAddress(Library, "TdhGetProperty")) == 0 )
      {
        dword_180077B00 = GetLastError();
      }
      Init_thread_footer(&dword_180077AF0);
    }
  }
  if ( dword_180077B00 || !qword_180077AF8 )
    return 1;
  else
    return qword_180077AF8(this, 0, 0, 1, a5, 4, a7);
}

```

## disassembly

```asm
0x180041fac  push    rbx
0x180041fae  sub     rsp, 40h
0x180041fb2  mov     edx, cs:_tls_index
0x180041fb8  mov     rbx, rcx
0x180041fbb  mov     rax, gs:58h
0x180041fc4  mov     ecx, 4
0x180041fc9  mov     rax, [rax+rdx*8]
0x180041fcd  mov     eax, [rcx+rax]
0x180041fd0  cmp     cs:dword_180077AF0, eax
0x180041fd6  jle     loc_180042095
0x180041fdc  lea     rcx, dword_180077AF0
0x180041fe3  call    _Init_thread_header
0x180041fe8  cmp     cs:dword_180077AF0, 0FFFFFFFFh
0x180041fef  jnz     loc_180042095
0x180041ff5  xor     edx, edx; hFile
0x180041ff7  mov     cs:qword_180077B04, 0
0x180042002  mov     r8d, 800h; dwFlags
0x180042008  mov     cs:dword_180077B0C, 0
0x180042012  lea     rcx, aApiMsWinEventi; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x180042019  mov     cs:qword_180077AF8, 0
0x180042024  mov     cs:dword_180077B00, 0
0x18004202e  call    cs:__imp_LoadLibraryExW
0x180042034  mov     cs:qword_180077B04+4, rax
0x18004203b  test    rax, rax
0x18004203e  jnz     short loc_180042061
0x180042040  xor     edx, edx; hFile
0x180042042  lea     rcx, LibFileName; "tdh.dll"
0x180042049  mov     r8d, 800h; dwFlags
0x18004204f  call    cs:__imp_LoadLibraryExW
0x180042055  mov     cs:qword_180077B04+4, rax
0x18004205c  test    rax, rax
0x18004205f  jz      short loc_18004207D
0x180042061  lea     rdx, aTdhgetproperty; "TdhGetProperty"
0x180042068  mov     rcx, rax; hModule
0x18004206b  call    cs:__imp_GetProcAddress
0x180042071  mov     cs:qword_180077AF8, rax
0x180042078  test    rax, rax
0x18004207b  jnz     short loc_180042089
0x18004207d  call    cs:__imp_GetLastError
0x180042083  mov     cs:dword_180077B00, eax
0x180042089  lea     rcx, dword_180077AF0
0x180042090  call    _Init_thread_footer
0x180042095  cmp     cs:dword_180077B00, 0
0x18004209c  jnz     short loc_1800420DF
0x18004209e  mov     rax, cs:qword_180077AF8
0x1800420a5  test    rax, rax
0x1800420a8  jz      short loc_1800420DF
0x1800420aa  mov     rcx, qword ptr [rsp+48h+arg_30]
0x1800420b2  mov     r9d, 1
0x1800420b8  mov     [rsp+48h+var_18], rcx
0x1800420bd  xor     r8d, r8d
0x1800420c0  mov     rcx, [rsp+48h+arg_20]
0x1800420c5  xor     edx, edx
0x1800420c7  mov     [rsp+48h+var_20], 4
0x1800420cf  mov     [rsp+48h+var_28], rcx
0x1800420d4  mov     rcx, rbx
0x1800420d7  call    cs:__guard_dispatch_icall_fptr
0x1800420dd  jmp     short loc_1800420E4
0x1800420df  mov     eax, 1
0x1800420e4  add     rsp, 40h
0x1800420e8  pop     rbx
0x1800420e9  retn
```
