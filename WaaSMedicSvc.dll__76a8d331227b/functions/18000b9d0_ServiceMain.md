# ServiceMain

- ea: `0x18000b9d0`
- end: `0x18000bab2`
- name: `ServiceMain`
- size: `226`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x18000279c`
- `0x180002804`
- `0x180003950`
- `0x180009f58`
- `0x18000a41c`
- `0x18000a958`
- `0x18000b3ec`
- `0x18000b9d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba52`

## string_xrefs

- `0x18000ba47`: `ServiceMain`
- `0x18000ba75`: `ServiceMain`

## pseudocode

```c
__int64 __fastcall ServiceMain(unsigned int a1, __int64 a2)
{
  __int64 result; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  struct uus::DllForwarder *DllForwarder; // rbx
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( dword_180013614 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180013614);
      if ( dword_180013614 == -1 )
      {
        DllForwarder = GetDllForwarder();
        ProcAddress = GetProcAddress(*((HMODULE *)DllForwarder + 2), "ServiceMain");
        if ( !ProcAddress )
        {
          std::wstring::c_str((char *)DllForwarder + 24);
          v9 = (const unsigned __int16 *)std::wstring::c_str((char *)DllForwarder + 56);
          uus::UndockedStubDllTelemetry::ProcNotFound("ServiceMain", v9, v10);
          v11 = wil::verify_hresult<long>(2147500033LL);
          wil::details::in1diag3::Throw_Hr(retaddr, v12, v13, (const char *)v11, v14);
        }
        qword_180013618 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
        Init_thread_footer(&dword_180013614);
      }
    }
    result = qword_180013618(a1, a2);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x39, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000b9d0  mov     [rsp+arg_0], rbx
0x18000b9d5  mov     [rsp+arg_8], rsi
0x18000b9da  push    rdi; int
0x18000b9db  sub     rsp, 20h
0x18000b9df  mov     rdi, rdx
0x18000b9e2  mov     esi, ecx
0x18000b9e4  mov     r8d, cs:_tls_index
0x18000b9eb  mov     rax, gs:58h
0x18000b9f4  mov     ecx, 4
0x18000b9f9  mov     rax, [rax+r8*8]
0x18000b9fd  mov     eax, [rcx+rax]
0x18000ba00  cmp     cs:dword_180013614, eax
0x18000ba06  jg      short loc_18000BA2A
0x18000ba08  mov     rdx, rdi
0x18000ba0b  mov     ecx, esi
0x18000ba0d  mov     rax, cs:qword_180013618
0x18000ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba19  nop
0x18000ba1a  mov     rbx, [rsp+28h+arg_0]
0x18000ba1f  mov     rsi, [rsp+28h+arg_8]
0x18000ba24  add     rsp, 20h
0x18000ba28  pop     rdi
0x18000ba29  retn
0x18000ba2a  lea     rcx, dword_180013614
0x18000ba31  call    _Init_thread_header
0x18000ba36  cmp     cs:dword_180013614, 0FFFFFFFFh
0x18000ba3d  jnz     short loc_18000BA08
0x18000ba3f  call    ?GetDllForwarder@@YAAEAUDllForwarder@uus@@XZ; GetDllForwarder(void)
0x18000ba44  mov     rbx, rax
0x18000ba47  lea     rdx, aServicemain_0; "ServiceMain"
0x18000ba4e  mov     rcx, [rax+10h]; hModule
0x18000ba52  call    cs:__imp_GetProcAddress
0x18000ba58  test    rax, rax
0x18000ba5b  jnz     short loc_18000BA98
0x18000ba5d  lea     rcx, [rbx+18h]
0x18000ba61  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18000ba66  mov     r8, rax
0x18000ba69  lea     rcx, [rbx+38h]
0x18000ba6d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18000ba72  mov     rdx, rax; unsigned __int16 *
0x18000ba75  lea     rcx, aServicemain_0; "ServiceMain"
0x18000ba7c  call    ?ProcNotFound@UndockedStubDllTelemetry@uus@@SAXPEBDPEBG1@Z; uus::UndockedStubDllTelemetry::ProcNotFound(char const *,ushort const *,ushort const *)
0x18000ba81  mov     ecx, 80004001h
0x18000ba86  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000ba8b  mov     r9d, eax; char *
0x18000ba8e  mov     rcx, [rsp+28h]; this
0x18000ba93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ba98  mov     cs:qword_180013618, rax
0x18000ba9f  lea     rcx, dword_180013614
0x18000baa6  call    _Init_thread_footer
0x18000baab  jmp     loc_18000BA08
```
