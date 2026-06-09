# Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)

- ea: `0x180074390`
- end: `0x180074420`
- name: `?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800398cc`

## callees

- `0x18000829c`
- `0x180074390`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180074403`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180074403`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800743a6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800743b7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800743a6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800743b7`

## pseudocode

```c
HRESULT __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::Register(
        Microsoft::Windows::Performance::CEtwPrivateLogger *this)
{
  HRESULT result; // eax
  ULONG v3; // eax

  result = CoCreateGuid((GUID *)this + 2);
  if ( result >= 0 )
  {
    result = CoCreateGuid((GUID *)this + 3);
    if ( result >= 0 )
    {
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 2) = (char *)this + 48;
      v3 = RegisterTraceGuidsW(
             (WMIDPREQUEST)XmlObjBase::OnElementText,
             0,
             (LPCGUID)this + 2,
             1u,
             (PTRACE_GUID_REGISTRATION)this + 1,
             0,
             0,
             (PTRACEHANDLE)this + 8);
      return ATL::AtlHresultFromWin32(v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180074390  mov     [rsp+arg_0], rbx
0x180074395  mov     [rsp+arg_8], rsi
0x18007439a  push    rdi
0x18007439b  sub     rsp, 40h
0x18007439f  mov     rbx, rcx
0x1800743a2  add     rcx, 20h ; ' '; pguid
0x1800743a6  call    cs:__imp_CoCreateGuid
0x1800743ac  test    eax, eax
0x1800743ae  js      short loc_180074410
0x1800743b0  lea     rdi, [rbx+30h]
0x1800743b4  mov     rcx, rdi; pguid
0x1800743b7  call    cs:__imp_CoCreateGuid
0x1800743bd  test    eax, eax
0x1800743bf  js      short loc_180074410
0x1800743c1  lea     rcx, [rbx+10h]
0x1800743c5  mov     qword ptr [rbx+18h], 0
0x1800743cd  lea     rax, [rbx+40h]
0x1800743d1  mov     [rcx], rdi
0x1800743d4  mov     [rsp+48h+RegistrationHandle], rax; RegistrationHandle
0x1800743d9  lea     r8, [rbx+20h]; ControlGuid
0x1800743dd  mov     [rsp+48h+MofResourceName], 0; MofResourceName
0x1800743e6  mov     r9d, 1; GuidCount
0x1800743ec  mov     [rsp+48h+MofImagePath], 0; MofImagePath
0x1800743f5  xor     edx, edx; RequestContext
0x1800743f7  mov     [rsp+48h+TraceGuidReg], rcx; TraceGuidReg
0x1800743fc  lea     rcx, ?OnElementText@XmlObjBase@@MEAAJPEAUIXmlReader@@PEBG@Z; RequestAddress
0x180074403  call    cs:__imp_RegisterTraceGuidsW
0x180074409  mov     ecx, eax; unsigned int
0x18007440b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180074410  mov     rbx, [rsp+48h+arg_0]
0x180074415  mov     rsi, [rsp+48h+arg_8]
0x18007441a  add     rsp, 40h
0x18007441e  pop     rdi
0x18007441f  retn
```
