# Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::GetCertBufferFromCertContext(_CERT_CONTEXT const *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180046c5c`
- end: `0x180046cff`
- name: `?GetCertBufferFromCertContext@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEBU_CERT_CONTEXT@@PEAPEAUIBuffer@Streams@Storage@5@@Z`
- size: `163`
- prototype: `static int(const struct _CERT_CONTEXT *, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046768`

## callees

- `0x180003bb6`
- `0x180006e8c`
- `0x180006eac`
- `0x18004576c`
- `0x180046c5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046cb7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::GetCertBufferFromCertContext(
        const struct _CERT_CONTEXT *a1,
        struct Windows::Storage::Streams::IBuffer **a2)
{
  void *v4; // rax
  const char *v5; // r9
  int v6; // edi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a2 = 0;
  v4 = CoTaskMemAlloc(a1->cbCertEncoded);
  v6 = (int)v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x131,
             (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
             v5);
  memcpy_0(v4, a1->pbCertEncoded, a1->cbCertEncoded);
  v8 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
         a1->cbCertEncoded,
         a1->cbCertEncoded,
         v6,
         (_DWORD)CoTaskMemFree,
         (__int64)a2);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x139,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
    (const char *)(unsigned int)v8,
    v10);
  return v9;
}

```

## disassembly

```asm
0x180046c5c  mov     [rsp+arg_0], rbx
0x180046c61  mov     [rsp+arg_8], rsi
0x180046c66  push    rdi
0x180046c67  sub     rsp, 30h
0x180046c6b  mov     rbx, rcx
0x180046c6e  mov     qword ptr [rdx], 0
0x180046c75  mov     ecx, [rcx+10h]; cb
0x180046c78  mov     rsi, rdx
0x180046c7b  call    cs:__imp_CoTaskMemAlloc
0x180046c81  mov     rdi, rax
0x180046c84  test    rax, rax
0x180046c87  jnz     short loc_180046CA1
0x180046c89  mov     rcx, [rsp+38h]; this
0x180046c8e  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180046c95  mov     edx, 131h; void *
0x180046c9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046c9f  jmp     short loc_180046CEF
0x180046ca1  mov     r8d, [rbx+10h]; Size
0x180046ca5  mov     rcx, rdi; void *
0x180046ca8  mov     rdx, [rbx+8]; Src
0x180046cac  call    memcpy_0
0x180046cb1  mov     ecx, [rbx+10h]
0x180046cb4  mov     r8, rdi
0x180046cb7  mov     r9, cs:__imp_CoTaskMemFree
0x180046cbe  mov     edx, ecx
0x180046cc0  mov     qword ptr [rsp+38h+var_18], rsi; int
0x180046cc5  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x180046cca  mov     ebx, eax
0x180046ccc  test    eax, eax
0x180046cce  jns     short loc_180046CED
0x180046cd0  mov     rcx, [rsp+38h]; this
0x180046cd5  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180046cdc  mov     r9d, eax; char *
0x180046cdf  mov     edx, 139h; void *
0x180046ce4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046ce9  mov     eax, ebx
0x180046ceb  jmp     short loc_180046CEF
0x180046ced  xor     eax, eax
0x180046cef  mov     rbx, [rsp+38h+arg_0]
0x180046cf4  mov     rsi, [rsp+38h+arg_8]
0x180046cf9  add     rsp, 30h
0x180046cfd  pop     rdi
0x180046cfe  retn
```
