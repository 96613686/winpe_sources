# Windows::UI::Composition::CompositionAnimation::ClearParameter(HSTRING__ *)

- ea: `0x18000e278`
- end: `0x18000e38f`
- name: `?ClearParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionAnimation *__hidden this, HSTRING)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180076f10`
- `0x180078ec0`
- `0x1800c6a90`
- `0x18015c9b0`

## callees

- `0x18000c924`
- `0x18000d8cc`
- `0x18000e278`
- `0x18000f334`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e324`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000e387`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000e387`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e30e`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000e30e`
- `ntdll!RtlLookupElementGenericTable` at `0x18000e2c5`
- `ntdll!RtlLookupElementGenericTable` at `0x18000e2c5`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimation::ClearParameter(
        Windows::UI::Composition::CompositionAnimation *this,
        HSTRING a2)
{
  struct _RTL_GENERIC_TABLE *v2; // rsi
  __int64 *v4; // rbx
  HSTRING v5; // rdi
  struct IUnknown *v7; // rdx
  Microsoft::WRL2::ContextSession *v8; // rcx
  HSTRING Buffer; // [rsp+20h] [rbp-39h] BYREF
  int v10; // [rsp+28h] [rbp-31h]
  __int128 v11; // [rsp+30h] [rbp-29h]
  int v12; // [rsp+40h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-1h] BYREF
  int v14; // [rsp+60h] [rbp+7h]
  __int128 v15; // [rsp+68h] [rbp+Fh]
  int v16; // [rsp+78h] [rbp+1Fh]

  v2 = (struct _RTL_GENERIC_TABLE *)((char *)this + 208);
  Buffer = a2;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v4 = (__int64 *)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 208), &Buffer);
  ParameterEntry::~ParameterEntry((ParameterEntry *)&Buffer);
  if ( v4 )
  {
    if ( *((_DWORD *)v4 + 8) == 2 )
    {
      --*((_DWORD *)this + 80);
      v7 = (struct IUnknown *)v4[3];
      if ( v7 )
      {
        v8 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
        v4[3] = 0;
        Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(v8, v7);
      }
      *((_DWORD *)v4 + 8) = 0;
      Windows::UI::Composition::CompositionAnimation::InvalidateCache(this);
    }
    v5 = (HSTRING)*v4;
    v13 = *v4;
    v15 = 0;
    v14 = 0;
    v16 = 0;
    ParameterEntry::~ParameterEntry((ParameterEntry *)v4);
    if ( !RtlDeleteElementGenericTable(v2, &v13) )
      RaiseFailFastException(0, 0, 1u);
    ParameterEntry::~ParameterEntry((ParameterEntry *)&v13);
    WindowsDeleteString(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e278  mov     [rsp-8+arg_10], rbx
0x18000e27d  push    rbp
0x18000e27e  push    rsi
0x18000e27f  push    rdi
0x18000e280  lea     rbp, [rsp-47h]
0x18000e285  sub     rsp, 0A0h
0x18000e28c  mov     rax, cs:__security_cookie
0x18000e293  xor     rax, rsp
0x18000e296  mov     [rbp+57h+var_20], rax
0x18000e29a  lea     rsi, [rcx+0D0h]
0x18000e2a1  mov     [rbp+57h+Buffer], rdx
0x18000e2a5  mov     rdi, rcx
0x18000e2a8  mov     [rbp+57h+var_88], 0
0x18000e2af  xorps   xmm0, xmm0
0x18000e2b2  mov     [rbp+57h+var_70], 0
0x18000e2b9  mov     rcx, rsi; Table
0x18000e2bc  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18000e2c0  movdqu  [rbp+57h+var_80], xmm0
0x18000e2c5  call    cs:__imp_RtlLookupElementGenericTable
0x18000e2cb  lea     rcx, [rbp+57h+Buffer]; this
0x18000e2cf  mov     rbx, rax
0x18000e2d2  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x18000e2d7  test    rbx, rbx
0x18000e2da  jz      short loc_18000E32A
0x18000e2dc  cmp     dword ptr [rbx+20h], 2
0x18000e2e0  jz      short loc_18000E34B
0x18000e2e2  mov     rdi, [rbx]
0x18000e2e5  xorps   xmm0, xmm0
0x18000e2e8  mov     rcx, rbx; this
0x18000e2eb  mov     [rbp+57h+var_58], rdi
0x18000e2ef  movdqu  [rbp+57h+var_48], xmm0
0x18000e2f4  mov     [rbp+57h+var_50], 0
0x18000e2fb  mov     [rbp+57h+var_38], 0
0x18000e302  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x18000e307  lea     rdx, [rbp+57h+var_58]; Buffer
0x18000e30b  mov     rcx, rsi; Table
0x18000e30e  call    cs:__imp_RtlDeleteElementGenericTable
0x18000e314  test    al, al
0x18000e316  jz      short loc_18000E37F
0x18000e318  lea     rcx, [rbp+57h+var_58]; this
0x18000e31c  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x18000e321  mov     rcx, rdi; string
0x18000e324  call    cs:__imp_WindowsDeleteString
0x18000e32a  xor     eax, eax
0x18000e32c  mov     rcx, [rbp+57h+var_20]
0x18000e330  xor     rcx, rsp; StackCookie
0x18000e333  call    __security_check_cookie
0x18000e338  mov     rbx, [rsp+0B0h+arg_10]
0x18000e340  add     rsp, 0A0h
0x18000e347  pop     rdi
0x18000e348  pop     rsi
0x18000e349  pop     rbp
0x18000e34a  retn
0x18000e34b  dec     dword ptr [rdi+140h]
0x18000e351  mov     rdx, [rbx+18h]; struct IUnknown *
0x18000e355  test    rdx, rdx
0x18000e358  jz      short loc_18000E36B
0x18000e35a  mov     rcx, [rdi+18h]; this
0x18000e35e  mov     qword ptr [rbx+18h], 0
0x18000e366  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x18000e36b  mov     rcx, rdi; this
0x18000e36e  mov     dword ptr [rbx+20h], 0
0x18000e375  call    ?InvalidateCache@CompositionAnimation@Composition@UI@Windows@@IEAAXXZ; Windows::UI::Composition::CompositionAnimation::InvalidateCache(void)
0x18000e37a  jmp     loc_18000E2E2
0x18000e37f  xor     edx, edx; pContextRecord
0x18000e381  xor     ecx, ecx; pExceptionRecord
0x18000e383  lea     r8d, [rdx+1]; dwFlags
0x18000e387  call    cs:__imp_RaiseFailFastException
0x18000e38d  jmp     short loc_18000E318
```
