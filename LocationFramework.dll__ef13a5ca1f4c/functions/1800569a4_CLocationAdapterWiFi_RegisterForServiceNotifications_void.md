# CLocationAdapterWiFi::RegisterForServiceNotifications(void)

- ea: `0x1800569a4`
- end: `0x180056a73`
- name: `?RegisterForServiceNotifications@CLocationAdapterWiFi@@QEAAKXZ`
- size: `207`
- prototype: `unsigned int __fastcall(CLocationAdapterWiFi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800565f4`

## callees

- `0x18001bb40`
- `0x1800569a4`
- `0x180056aac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569d4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800569e9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800569e9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800569c2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800569c2`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180056a19`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180056a19`

## string_xrefs

- `0x1800569b1`: `ServicesActive`
- `0x180056a36`: `CLocationAdapterWiFi::RegisterForServiceNotifications`

## pseudocode

```c
__int64 __fastcall CLocationAdapterWiFi::RegisterForServiceNotifications(CLocationAdapterWiFi *this)
{
  SC_HANDLE v2; // rax
  signed int LastError; // eax
  SC_HANDLE v4; // rax
  unsigned int v5; // ebx
  char *v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+30h] [rbp-8h]
  wil::details::in1diag5 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 4u);
  *((_QWORD *)this + 31) = v2;
  if ( v2 && (v4 = OpenServiceW(v2, *((LPCWSTR *)this + 34), 4u), (*((_QWORD *)this + 32) = v4) != 0) )
    LastError = SubscribeServiceChangeNotifications(
                  v4,
                  2,
                  CLocationAdapterWiFi::ScmEventsCallback,
                  this,
                  (char *)this + 264);
  else
    LastError = GetLastError();
  v5 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v7) = LastError;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\wifiadapter\\locationadapterwifi.cpp",
      "CLocationAdapterWiFi::RegisterForServiceNotifications",
      "HRESULT_FROM_WIN32(error)",
      v7,
      v8);
    CLocationAdapterWiFi::UnregisterForServiceNotifications(this);
  }
  return v5;
}

```

## disassembly

```asm
0x1800569a4  mov     [rsp+arg_0], rbx
0x1800569a9  push    rdi; int
0x1800569aa  sub     rsp, 30h
0x1800569ae  mov     rdi, rcx
0x1800569b1  lea     rdx, DatabaseName; "ServicesActive"
0x1800569b8  mov     ebx, 4
0x1800569bd  xor     ecx, ecx; lpMachineName
0x1800569bf  mov     r8d, ebx; dwDesiredAccess
0x1800569c2  call    cs:__imp_OpenSCManagerW
0x1800569c8  mov     [rdi+0F8h], rax
0x1800569cf  test    rax, rax
0x1800569d2  jnz     short loc_1800569DC
0x1800569d4  call    cs:__imp_GetLastError
0x1800569da  jmp     short loc_180056A1F
0x1800569dc  mov     rdx, [rdi+110h]; lpServiceName
0x1800569e3  mov     r8d, ebx; dwDesiredAccess
0x1800569e6  mov     rcx, rax; hSCManager
0x1800569e9  call    cs:__imp_OpenServiceW
0x1800569ef  mov     [rdi+100h], rax
0x1800569f6  mov     rcx, rax
0x1800569f9  test    rax, rax
0x1800569fc  jz      short loc_1800569D4
0x1800569fe  lea     rax, [rdi+108h]
0x180056a05  mov     r9, rdi
0x180056a08  lea     r8, ?ScmEventsCallback@CLocationAdapterWiFi@@SAXKPEAX@Z; CLocationAdapterWiFi::ScmEventsCallback(ulong,void *)
0x180056a0f  mov     [rsp+38h+var_18], rax
0x180056a14  mov     edx, 2
0x180056a19  call    cs:__imp_SubscribeServiceChangeNotifications
0x180056a1f  mov     ebx, eax
0x180056a21  test    eax, eax
0x180056a23  jz      short loc_180056A66
0x180056a25  jg      short loc_180056A29
0x180056a27  jmp     short loc_180056A31
0x180056a29  movzx   eax, bx
0x180056a2c  or      eax, 80070000h
0x180056a31  mov     rcx, [rsp+38h]; this
0x180056a36  lea     r9, aClocationadapt_7; "CLocationAdapterWiFi::RegisterForServic"...
0x180056a3d  mov     dword ptr [rsp+38h+var_10], eax; char *
0x180056a41  lea     r8, aOnecoreuapDriv_25; "onecoreuap\\drivers\\mobilepc\\location"...
0x180056a48  lea     rax, aHresultFromWin_1; "HRESULT_FROM_WIN32(error)"
0x180056a4f  mov     edx, 0A8h; void *
0x180056a54  mov     [rsp+38h+var_18], rax; char *
0x180056a59  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180056a5e  mov     rcx, rdi; this
0x180056a61  call    ?UnregisterForServiceNotifications@CLocationAdapterWiFi@@QEAAXXZ; CLocationAdapterWiFi::UnregisterForServiceNotifications(void)
0x180056a66  mov     eax, ebx
0x180056a68  mov     rbx, [rsp+38h+arg_0]
0x180056a6d  add     rsp, 30h
0x180056a71  pop     rdi
0x180056a72  retn
```
