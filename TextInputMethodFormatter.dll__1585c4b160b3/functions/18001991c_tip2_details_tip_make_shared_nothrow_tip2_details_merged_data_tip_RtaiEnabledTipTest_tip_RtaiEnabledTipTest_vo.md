# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>,>(void)

- ea: `0x18001991c`
- end: `0x180019a3d`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019810`

## callees

- `0x180007a48`
- `0x18001991c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019a01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019a01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001992e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001992e`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable';
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
  *(_DWORD *)(v3 + 42) = 0;
  *((_WORD *)v3 + 23) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 45036609;
  *((_DWORD *)v3 + 7) = 49408;
  *((_QWORD *)v3 + 4) = "RtaiEnabledTipTest";
  *((_WORD *)v3 + 20) = 1;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_DWORD *)v3 + 68) = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18001991c  mov     [rsp+arg_0], rbx
0x180019921  push    rdi
0x180019922  sub     rsp, 20h
0x180019926  mov     rdi, rcx
0x180019929  mov     ecx, 118h; cb
0x18001992e  call    cs:__imp_CoTaskMemAlloc
0x180019934  xor     r9d, r9d
0x180019937  mov     rbx, rax
0x18001993a  test    rax, rax
0x18001993d  jz      loc_180019A37
0x180019943  xor     r8d, r8d
0x180019946  lea     rax, ??_7?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextReconversionCandidatesUpdatingEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextReconversionCandidatesUpdatingEventArgs *>::`vftable'
0x18001994d  mov     [rbx], rax
0x180019950  lea     rdx, aRtaienabledtip; "RtaiEnabledTipTest"
0x180019957  mov     [rbx+10h], r9
0x18001995b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180019962  mov     [rbx+8], rbx
0x180019966  xorps   xmm0, xmm0
0x180019969  mov     [rbx+50h], r9
0x18001996d  mov     [rbx+58h], r9
0x180019971  mov     [rbx+60h], r9
0x180019975  mov     [rbx+68h], r9
0x180019979  mov     [rbx+70h], r9
0x18001997d  mov     [rbx+78h], r9
0x180019981  mov     [rbx+80h], r9
0x180019988  mov     [rbx+88h], r9
0x18001998f  mov     [rbx+90h], r9
0x180019996  mov     [rbx+48h], r9d
0x18001999a  movups  xmmword ptr [rbx+98h], xmm0
0x1800199a1  mov     [rbx+0A8h], r9b
0x1800199a8  mov     word ptr [rbx+0AAh], 0FFFFh
0x1800199b1  mov     [rbx+0B0h], r9
0x1800199b8  mov     [rbx+0B8h], r9
0x1800199bf  mov     [rbx+0F8h], r9
0x1800199c6  mov     [rbx+2Ah], r8d
0x1800199ca  mov     [rbx+2Eh], r8w
0x1800199cf  mov     [rbx+0C0h], r9d
0x1800199d6  mov     [rbx+0F0h], r9d
0x1800199dd  mov     dword ptr [rbx+18h], 2AF3441h
0x1800199e4  mov     dword ptr [rbx+1Ch], 0C100h
0x1800199eb  mov     [rbx+20h], rdx
0x1800199ef  mov     word ptr [rbx+28h], 1
0x1800199f5  mov     [rbx+30h], r9
0x1800199f9  mov     [rbx+38h], r9
0x1800199fd  mov     [rbx+40h], r9
0x180019a01  call    cs:__imp_InitializeCriticalSection
0x180019a07  lea     rax, ??_7?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::`vftable'
0x180019a0e  mov     dword ptr [rbx+110h], 1
0x180019a18  mov     [rbx], rax
0x180019a1b  lea     rax, [rbx+10h]
0x180019a1f  mov     [rbx+108h], rax
0x180019a26  mov     rax, rdi
0x180019a29  mov     [rdi], rbx
0x180019a2c  mov     rbx, [rsp+28h+arg_0]
0x180019a31  add     rsp, 20h
0x180019a35  pop     rdi
0x180019a36  retn
0x180019a37  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
