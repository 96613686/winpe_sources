# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>,>(void)

- ea: `0x18002ff90`
- end: `0x1800300c9`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053f60`

## callees

- `0x18000c008`
- `0x18002ff90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030076`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ffa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ffa7`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x128u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &winrt::impl::producers_base<BufferOverPointer,std::tuple<winrt::Windows::Storage::Streams::IBuffer,winrt::Windows::Storage::Streams::IOutputStream,Windows::Storage::Streams::IBufferByteAccess>>::`vftable';
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
  *((_DWORD *)v3 + 6) = 59221156;
  *((_DWORD *)v3 + 7) = 17152;
  *((_QWORD *)v3 + 4) = "AutoCategorizationTest";
  *((_WORD *)v3 + 20) = 2;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  v3[280] = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  *((_QWORD *)v3 + 34) = 3;
  *((_DWORD *)v3 + 72) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18002ff90  mov     [rsp+arg_0], rbx
0x18002ff95  mov     [rsp+arg_8], rsi
0x18002ff9a  push    rdi
0x18002ff9b  sub     rsp, 20h
0x18002ff9f  mov     rdi, rcx
0x18002ffa2  mov     ecx, 128h; cb
0x18002ffa7  call    cs:__imp_CoTaskMemAlloc
0x18002ffad  xor     esi, esi
0x18002ffaf  mov     rbx, rax
0x18002ffb2  test    rax, rax
0x18002ffb5  jz      loc_1800300C3
0x18002ffbb  xor     r8d, r8d
0x18002ffbe  lea     rax, ??_7?$producers_base@UBufferOverPointer@@V?$tuple@UIBuffer@Streams@Storage@Windows@winrt@@UIOutputStream@2345@UIBufferByteAccess@234@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<BufferOverPointer,std::tuple<winrt::Windows::Storage::Streams::IBuffer,winrt::Windows::Storage::Streams::IOutputStream,Windows::Storage::Streams::IBufferByteAccess>>::`vftable'
0x18002ffc5  mov     [rbx], rax
0x18002ffc8  lea     rdx, aAutocategoriza; "AutoCategorizationTest"
0x18002ffcf  mov     [rbx+10h], rsi
0x18002ffd3  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002ffda  mov     [rbx+8], rbx
0x18002ffde  xorps   xmm0, xmm0
0x18002ffe1  mov     [rbx+50h], rsi
0x18002ffe5  mov     [rbx+58h], rsi
0x18002ffe9  mov     [rbx+60h], rsi
0x18002ffed  mov     [rbx+68h], rsi
0x18002fff1  mov     [rbx+70h], rsi
0x18002fff5  mov     [rbx+78h], rsi
0x18002fff9  mov     [rbx+80h], rsi
0x180030000  mov     [rbx+88h], rsi
0x180030007  mov     [rbx+90h], rsi
0x18003000e  mov     [rbx+48h], esi
0x180030011  movups  xmmword ptr [rbx+98h], xmm0
0x180030018  mov     [rbx+0A8h], sil
0x18003001f  mov     word ptr [rbx+0AAh], 0FFFFh
0x180030028  mov     [rbx+0B0h], rsi
0x18003002f  mov     [rbx+0B8h], rsi
0x180030036  mov     [rbx+0F8h], rsi
0x18003003d  mov     [rbx+2Ah], r8d
0x180030041  mov     [rbx+2Eh], r8w
0x180030046  mov     [rbx+0C0h], esi
0x18003004c  mov     [rbx+0F0h], esi
0x180030052  mov     dword ptr [rbx+18h], 387A4A4h
0x180030059  mov     dword ptr [rbx+1Ch], 4300h
0x180030060  mov     [rbx+20h], rdx
0x180030064  mov     word ptr [rbx+28h], 2
0x18003006a  mov     [rbx+30h], rsi
0x18003006e  mov     [rbx+38h], rsi
0x180030072  mov     [rbx+40h], rsi
0x180030076  call    cs:__imp_InitializeCriticalSection
0x18003007c  mov     [rbx+118h], sil
0x180030083  lea     rax, ??_7?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::`vftable'
0x18003008a  mov     rsi, [rsp+28h+arg_8]
0x18003008f  mov     [rbx], rax
0x180030092  lea     rax, [rbx+10h]
0x180030096  mov     [rbx+108h], rax
0x18003009d  mov     rax, rdi
0x1800300a0  mov     qword ptr [rbx+110h], 3
0x1800300ab  mov     dword ptr [rbx+120h], 1
0x1800300b5  mov     [rdi], rbx
0x1800300b8  mov     rbx, [rsp+28h+arg_0]
0x1800300bd  add     rsp, 20h
0x1800300c1  pop     rdi
0x1800300c2  retn
0x1800300c3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
