# SvchostPushServiceGlobals

- ea: `0x18000bac0`
- end: `0x18000bb93`
- name: `SvchostPushServiceGlobals`
- size: `211`
- prototype: `__int64 __fastcall(__int64)`
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
- `0x18000bac0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb33`

## string_xrefs

- `0x18000bb28`: `SvchostPushServiceGlobals`
- `0x18000bb56`: `SvchostPushServiceGlobals`

## pseudocode

```c
__int64 __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  struct uus::DllForwarder *DllForwarder; // rbx
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r8
  unsigned int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( dword_180013620 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180013620);
      if ( dword_180013620 == -1 )
      {
        DllForwarder = GetDllForwarder();
        ProcAddress = GetProcAddress(*((HMODULE *)DllForwarder + 2), "SvchostPushServiceGlobals");
        if ( !ProcAddress )
        {
          std::wstring::c_str((char *)DllForwarder + 24);
          v7 = (const unsigned __int16 *)std::wstring::c_str((char *)DllForwarder + 56);
          uus::UndockedStubDllTelemetry::ProcNotFound("SvchostPushServiceGlobals", v7, v8);
          v9 = wil::verify_hresult<long>(2147500033LL);
          wil::details::in1diag3::Throw_Hr(retaddr, v10, v11, (const char *)v9, v12);
        }
        qword_180013628 = (__int64 (__fastcall *)(_QWORD))ProcAddress;
        Init_thread_footer(&dword_180013620);
      }
    }
    result = qword_180013628(a1);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x40, v3, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000bac0  mov     [rsp+arg_0], rbx
0x18000bac5  push    rdi; int
0x18000bac6  sub     rsp, 20h
0x18000baca  mov     rdi, rcx
0x18000bacd  mov     edx, cs:_tls_index
0x18000bad3  mov     rax, gs:58h
0x18000badc  mov     ecx, 4
0x18000bae1  mov     rax, [rax+rdx*8]
0x18000bae5  mov     eax, [rcx+rax]
0x18000bae8  cmp     cs:dword_180013620, eax
0x18000baee  jg      short loc_18000BB0B
0x18000baf0  mov     rcx, rdi
0x18000baf3  mov     rax, cs:qword_180013628
0x18000bafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baff  nop
0x18000bb00  mov     rbx, [rsp+28h+arg_0]
0x18000bb05  add     rsp, 20h
0x18000bb09  pop     rdi
0x18000bb0a  retn
0x18000bb0b  lea     rcx, dword_180013620
0x18000bb12  call    _Init_thread_header
0x18000bb17  cmp     cs:dword_180013620, 0FFFFFFFFh
0x18000bb1e  jnz     short loc_18000BAF0
0x18000bb20  call    ?GetDllForwarder@@YAAEAUDllForwarder@uus@@XZ; GetDllForwarder(void)
0x18000bb25  mov     rbx, rax
0x18000bb28  lea     rdx, aSvchostpushser_0; "SvchostPushServiceGlobals"
0x18000bb2f  mov     rcx, [rax+10h]; hModule
0x18000bb33  call    cs:__imp_GetProcAddress
0x18000bb39  test    rax, rax
0x18000bb3c  jnz     short loc_18000BB79
0x18000bb3e  lea     rcx, [rbx+18h]
0x18000bb42  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18000bb47  mov     r8, rax
0x18000bb4a  lea     rcx, [rbx+38h]
0x18000bb4e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18000bb53  mov     rdx, rax; unsigned __int16 *
0x18000bb56  lea     rcx, aSvchostpushser_0; "SvchostPushServiceGlobals"
0x18000bb5d  call    ?ProcNotFound@UndockedStubDllTelemetry@uus@@SAXPEBDPEBG1@Z; uus::UndockedStubDllTelemetry::ProcNotFound(char const *,ushort const *,ushort const *)
0x18000bb62  mov     ecx, 80004001h
0x18000bb67  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000bb6c  mov     r9d, eax; char *
0x18000bb6f  mov     rcx, [rsp+28h]; this
0x18000bb74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bb79  mov     cs:qword_180013628, rax
0x18000bb80  lea     rcx, dword_180013620
0x18000bb87  call    _Init_thread_footer
0x18000bb8c  jmp     loc_18000BAF0
```
