# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>,>(void)

- ea: `0x140052990`
- end: `0x140052ac2`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `306`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140056784`

## callees

- `0x14000a698`
- `0x140052990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140052a73`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140052a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400529a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400529a7`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x128u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable';
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *((_QWORD *)v3 + 4) = "MmpcDualEnrollmentTipTest";
  *(_DWORD *)(v3 + 42) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 60541452;
  *((_DWORD *)v3 + 7) = 53760;
  *((_WORD *)v3 + 20) = 769;
  *((_WORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_QWORD *)v3 + 34) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  v3[280] = 0;
  *((_DWORD *)v3 + 72) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x140052990  mov     [rsp+arg_0], rbx
0x140052995  mov     [rsp+arg_8], rsi
0x14005299a  push    rdi
0x14005299b  sub     rsp, 20h
0x14005299f  mov     rdi, rcx
0x1400529a2  mov     ecx, 128h; cb
0x1400529a7  call    cs:__imp_CoTaskMemAlloc
0x1400529ad  xor     esi, esi
0x1400529af  mov     rbx, rax
0x1400529b2  test    rax, rax
0x1400529b5  jz      loc_140052ABC
0x1400529bb  xor     edx, edx
0x1400529bd  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable'
0x1400529c4  mov     [rbx], rax
0x1400529c7  lea     rcx, aMmpcdualenroll; "MmpcDualEnrollmentTipTest"
0x1400529ce  mov     [rbx+10h], rsi
0x1400529d2  xorps   xmm0, xmm0
0x1400529d5  mov     [rbx+8], rbx
0x1400529d9  mov     [rbx+50h], rsi
0x1400529dd  mov     [rbx+58h], rsi
0x1400529e1  mov     [rbx+60h], rsi
0x1400529e5  mov     [rbx+68h], rsi
0x1400529e9  mov     [rbx+70h], rsi
0x1400529ed  mov     [rbx+78h], rsi
0x1400529f1  mov     [rbx+80h], rsi
0x1400529f8  mov     [rbx+88h], rsi
0x1400529ff  mov     [rbx+90h], rsi
0x140052a06  mov     [rbx+48h], esi
0x140052a09  movups  xmmword ptr [rbx+98h], xmm0
0x140052a10  mov     [rbx+0A8h], sil
0x140052a17  mov     word ptr [rbx+0AAh], 0FFFFh
0x140052a20  mov     [rbx+0B0h], rsi
0x140052a27  mov     [rbx+0B8h], rsi
0x140052a2e  mov     [rbx+0F8h], rsi
0x140052a35  mov     [rbx+20h], rcx
0x140052a39  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140052a40  mov     [rbx+2Ah], edx
0x140052a43  mov     [rbx+0C0h], esi
0x140052a49  mov     [rbx+0F0h], esi
0x140052a4f  mov     dword ptr [rbx+18h], 39BCA0Ch
0x140052a56  mov     dword ptr [rbx+1Ch], 0D200h
0x140052a5d  mov     word ptr [rbx+28h], 301h
0x140052a63  mov     [rbx+2Eh], dx
0x140052a67  mov     [rbx+30h], rsi
0x140052a6b  mov     [rbx+38h], rsi
0x140052a6f  mov     [rbx+40h], rsi
0x140052a73  call    cs:__imp_InitializeCriticalSection
0x140052a79  mov     [rbx+110h], rsi
0x140052a80  lea     rax, ??_7?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::`vftable'
0x140052a87  mov     [rbx], rax
0x140052a8a  lea     rax, [rbx+10h]
0x140052a8e  mov     [rbx+108h], rax
0x140052a95  mov     rax, rdi
0x140052a98  mov     [rbx+118h], sil
0x140052a9f  mov     rsi, [rsp+28h+arg_8]
0x140052aa4  mov     dword ptr [rbx+120h], 1
0x140052aae  mov     [rdi], rbx
0x140052ab1  mov     rbx, [rsp+28h+arg_0]
0x140052ab6  add     rsp, 20h
0x140052aba  pop     rdi
0x140052abb  retn
0x140052abc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
