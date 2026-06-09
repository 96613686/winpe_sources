# win_musl::FiberThread::ThreadProc(win_mp_lib::null_type)

- ea: `0x180020fd0`
- end: `0x18002116c`
- name: `?ThreadProc@FiberThread@win_musl@@AEAAXVnull_type@win_mp_lib@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000310c`
- `0x180020fd0`
- `0x180021698`
- `0x1800216cc`
- `0x18005a388`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002102e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002102e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002100f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800210f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002100f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800210f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021149`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020fe6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020fe6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021161`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021161`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x180020ff8`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x180020ff8`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18002108f`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18002108f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall win_musl::FiberThread::ThreadProc(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // edi
  LPVOID v4; // rax
  win_musl::CriticalSection *v5; // rbx
  __int64 v6; // r14
  win_musl::FiberBase *v7; // rbx
  __m128i v8; // xmm6
  unsigned __int64 v9; // xmm0_8
  DWORD LastError; // eax
  __m128i v11; // [rsp+20h] [rbp-48h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = -2147221008;
  if ( v2 != -2147221008 )
    v3 = v2;
  v4 = ConvertThreadToFiber(0);
  *(_QWORD *)(a1 + 16) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    *(_DWORD *)(a1 + 24) = LastError;
  }
  SetEvent(*(HANDLE *)(a1 + 72));
  while ( 1 )
  {
    WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
    v5 = (win_musl::CriticalSection *)(*(_QWORD *)(a1 + 8) + 16LL);
    win_musl::CriticalSection::Enter(v5);
    if ( *(_BYTE *)(a1 + 28) )
      break;
    if ( v5 )
      win_musl::CriticalSection::Leave(v5);
    v6 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(v6 + 64) = a1;
    SwitchToFiber(*(LPVOID *)(v6 + 32));
    v7 = *(win_musl::FiberBase **)(a1 + 40);
    if ( v7 && dword_180229950 != -1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      win_musl::FiberBase::ClearFiberState(v7);
      (*(void (__fastcall **)(win_musl::FiberBase *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( *(_QWORD *)(a1 + 48) )
    {
      if ( *(_QWORD *)(a1 + 56) )
      {
        if ( dword_180229950 != -1 )
        {
          v8 = *(__m128i *)(a1 + 48);
          *(_QWORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          v11 = v8;
          v9 = _mm_srli_si128(v8, 8).m128i_u64[0];
          SetEvent(*(HANDLE *)(v9 + 16));
          if ( v8.m128i_i64[0] )
          {
            if ( v9 )
              ___close_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl_____counted_strong_U__const_policies_U__types_6_Uclose_delete_win_scope__Uconvert_forbidden_2_Uacquire_none_2_U__normal_store_U__invalid_value_policy_Unull_t_win_scope___win_scope__Usafe_types_detach_forbidden_2__2_U__unique_policy__0A__2_Ureport_policy_throw_2__win_scope___win_scope___win_scope__SAXPEAU__counted_store_PEAV__DefaultContentHandler_V__XmlParser_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___consumption_win_musl___consumption_win_musl___1__Z(&v11);
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v5 )
    win_musl::CriticalSection::Leave(v5);
  if ( v3 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180020fd0  push    rbx
0x180020fd2  push    rsi
0x180020fd3  push    rdi
0x180020fd4  push    r14
0x180020fd6  sub     rsp, 48h
0x180020fda  movaps  [rsp+68h+var_38], xmm6
0x180020fdf  mov     rsi, rcx
0x180020fe2  xor     edx, edx; dwCoInit
0x180020fe4  xor     ecx, ecx; pvReserved
0x180020fe6  call    cs:__imp_CoInitializeEx
0x180020fec  mov     edi, 800401F0h
0x180020ff1  cmp     eax, edi
0x180020ff3  cmovnz  edi, eax
0x180020ff6  xor     ecx, ecx; lpParameter
0x180020ff8  call    cs:__imp_ConvertThreadToFiber
0x180020ffe  mov     [rsi+10h], rax
0x180021002  test    rax, rax
0x180021005  jz      loc_180021149
0x18002100b  mov     rcx, [rsi+48h]; hEvent
0x18002100f  call    cs:__imp_SetEvent
0x180021015  jmp     short loc_180021027
0x180021017  mov     rax, [r14]
0x18002101a  mov     rcx, r14
0x18002101d  mov     rax, [rax+10h]
0x180021021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021026  nop
0x180021027  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002102a  mov     rcx, [rsi+58h]; hHandle
0x18002102e  call    cs:__imp_WaitForSingleObject
0x180021034  mov     rbx, [rsi+8]
0x180021038  add     rbx, 10h
0x18002103c  mov     rcx, rbx; this
0x18002103f  call    ?Enter@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Enter(void)
0x180021044  cmp     byte ptr [rsi+1Ch], 0
0x180021048  jz      short loc_18002106E
0x18002104a  test    rbx, rbx
0x18002104d  jz      short loc_180021057
0x18002104f  mov     rcx, rbx; this
0x180021052  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x180021057  test    edi, edi
0x180021059  jns     loc_180021161
0x18002105f  movaps  xmm6, [rsp+68h+var_38]
0x180021064  add     rsp, 48h
0x180021068  pop     r14
0x18002106a  pop     rdi
0x18002106b  pop     rsi
0x18002106c  pop     rbx
0x18002106d  retn
0x18002106e  test    rbx, rbx
0x180021071  jz      short loc_18002107B
0x180021073  mov     rcx, rbx; this
0x180021076  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x18002107b  mov     r14, [rsi+20h]
0x18002107f  mov     qword ptr [rsi+20h], 0
0x180021087  mov     [r14+40h], rsi
0x18002108b  mov     rcx, [r14+20h]; lpFiber
0x18002108f  call    cs:__imp_SwitchToFiber
0x180021095  mov     rbx, [rsi+28h]
0x180021099  test    rbx, rbx
0x18002109c  jz      short loc_1800210A7
0x18002109e  cmp     cs:dword_180229950, 0FFFFFFFFh
0x1800210a5  jnz     short loc_180021123
0x1800210a7  cmp     qword ptr [rsi+30h], 0
0x1800210ac  jz      loc_180021017
0x1800210b2  cmp     qword ptr [rsi+38h], 0
0x1800210b7  jz      loc_180021017
0x1800210bd  cmp     cs:dword_180229950, 0FFFFFFFFh
0x1800210c4  jz      loc_180021017
0x1800210ca  movups  xmm6, xmmword ptr [rsi+30h]
0x1800210ce  mov     qword ptr [rsi+30h], 0
0x1800210d6  mov     qword ptr [rsi+38h], 0
0x1800210de  movdqa  [rsp+68h+var_48], xmm6
0x1800210e4  movdqa  xmm0, xmm6
0x1800210e8  psrldq  xmm0, 8
0x1800210ed  movq    rbx, xmm0
0x1800210f2  mov     rcx, [rbx+10h]; hEvent
0x1800210f6  call    cs:__imp_SetEvent
0x1800210fc  nop
0x1800210fd  movq    rax, xmm6
0x180021102  test    rax, rax
0x180021105  jz      loc_180021017
0x18002110b  test    rbx, rbx
0x18002110e  jz      loc_180021017
0x180021114  lea     rcx, [rsp+68h+var_48]
0x180021119  call    ??$close@PEAV?$DefaultContentHandler@V?$XmlParser@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@consumption@win_musl@@@consumption@win_musl@@@?$counted_strong@U?$const_policies@U?$types_6@Uclose_delete@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAV?$DefaultContentHandler@V?$XmlParser@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@consumption@win_musl@@@consumption@win_musl@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>> *>(win_scope::counted_store<win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>> *> *)
0x18002111e  jmp     loc_180021017
0x180021123  mov     qword ptr [rsi+28h], 0
0x18002112b  mov     rcx, rbx; this
0x18002112e  call    ?ClearFiberState@FiberBase@win_musl@@IEAAXXZ; win_musl::FiberBase::ClearFiberState(void)
0x180021133  nop
0x180021134  mov     rax, [rbx]
0x180021137  mov     rcx, rbx
0x18002113a  mov     rax, [rax+10h]
0x18002113e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021143  nop
0x180021144  jmp     loc_1800210A7
0x180021149  call    cs:__imp_GetLastError
0x18002114f  mov     ecx, 1
0x180021154  test    eax, eax
0x180021156  cmovz   eax, ecx
0x180021159  mov     [rsi+18h], eax
0x18002115c  jmp     loc_18002100B
0x180021161  call    cs:__imp_CoUninitialize
0x180021167  jmp     loc_18002105F
```
