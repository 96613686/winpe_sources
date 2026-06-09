# CRemoteTextAppIntegrationFactory::GetForCurrentThread(_GUID,Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration * *)

- ea: `0x18001cae0`
- end: `0x18001cbf5`
- name: `?GetForCurrentThread@CRemoteTextAppIntegrationFactory@@UEAAJU_GUID@@PEAPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(CRemoteTextAppIntegrationFactory *__hidden this, struct _GUID *__struct_ptr, struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003058`
- `0x1800132f0`
- `0x180014b90`
- `0x180018e44`
- `0x18001cae0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001cbcb`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001cbcb`

## string_xrefs

- `0x18001cb1a`: `CRemoteTextAppIntegrationFactory::GetForCurrentThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteTextAppIntegrationFactory::GetForCurrentThread(
        CRemoteTextAppIntegrationFactory *this,
        struct _GUID *a2,
        struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  _QWORD *v8; // rdi
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  unsigned __int64 retaddr; // [rsp+38h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v7 = *(_DWORD *)(v6 + 304);
    v8 = (_QWORD *)(v6 + 312);
    if ( (v7 & 1) == 0 )
    {
      *(_DWORD *)(v6 + 304) = v7 | 1;
      *v8 = 0;
      _tlregdtor(CRemoteTextAppIntegrationFactory::GetForCurrentThread_::_2_::_dynamic_atexit_destructor_for__threadInstance__);
    }
    if ( *v8
      || (v9 = Microsoft::WRL::Details::MakeAndInitialize<CRemoteTextAppIntegration,CRemoteTextAppIntegration,_GUID &>(
                 v8,
                 a2),
          v5 = v9,
          v9 >= 0) )
    {
      v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration **))*v8)(
              *v8,
              &GUID_ac4530f6_68f2_48b7_803c_647212e1e4be,
              a3);
      v5 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -2147024882 )
          TerminateProcessOnMemoryExhaustion(0);
        FailFastWithHR(v5, retaddr, 0x69Du);
      }
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      McTemplateU0sqq_EventWriteTransfer(
        v11,
        v10,
        (unsigned int)"CRemoteTextAppIntegrationFactory::GetForCurrentThread",
        1690,
        v9);
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (unsigned int)"CRemoteTextAppIntegrationFactory::GetForCurrentThread",
        1684,
        87);
  }
  return v5;
}

```

## disassembly

```asm
0x18001cae0  mov     [rsp+arg_0], rbx
0x18001cae5  mov     [rsp+arg_18], rsi
0x18001caea  push    rdi
0x18001caeb  sub     rsp, 30h
0x18001caef  mov     rsi, r8
0x18001caf2  mov     rbx, rdx
0x18001caf5  test    r8, r8
0x18001caf8  jnz     short loc_18001CB2B
0x18001cafa  mov     ebx, 80070057h
0x18001caff  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001cb06  jz      loc_18001CBE3
0x18001cb0c  mov     [rsp+38h+var_18], 80070057h
0x18001cb14  mov     r9d, 694h
0x18001cb1a  lea     r8, aCremotetextapp_1; "CRemoteTextAppIntegrationFactory::GetFo"...
0x18001cb21  call    McTemplateU0sqq_EventWriteTransfer
0x18001cb26  jmp     loc_18001CBE3
0x18001cb2b  mov     qword ptr [r8], 0
0x18001cb32  mov     ecx, cs:_tls_index
0x18001cb38  mov     rax, gs:58h
0x18001cb41  mov     rdx, [rax+rcx*8]
0x18001cb45  mov     r8d, 130h
0x18001cb4b  mov     eax, [r8+rdx]
0x18001cb4f  mov     edi, 138h
0x18001cb54  add     rdi, rdx
0x18001cb57  test    al, 1
0x18001cb59  jnz     short loc_18001CB75
0x18001cb5b  or      eax, 1
0x18001cb5e  mov     [r8+rdx], eax
0x18001cb62  mov     qword ptr [rdi], 0
0x18001cb69  lea     rcx, _CRemoteTextAppIntegrationFactory__GetForCurrentThread____2____dynamic_atexit_destructor_for__threadInstance__
0x18001cb70  call    __tlregdtor
0x18001cb75  cmp     qword ptr [rdi], 0
0x18001cb79  jnz     short loc_18001CBA4
0x18001cb7b  mov     rdx, rbx
0x18001cb7e  mov     rcx, rdi
0x18001cb81  call    ??$MakeAndInitialize@VCRemoteTextAppIntegration@@V1@AEAU_GUID@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCRemoteTextAppIntegration@@@WRL@Microsoft@@@012@AEAU_GUID@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRemoteTextAppIntegration,CRemoteTextAppIntegration,_GUID &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CRemoteTextAppIntegration>>,_GUID &)
0x18001cb86  mov     ebx, eax
0x18001cb88  test    eax, eax
0x18001cb8a  jns     short loc_18001CBA4
0x18001cb8c  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001cb93  jz      short loc_18001CBE3
0x18001cb95  mov     [rsp+38h+var_18], eax
0x18001cb99  mov     r9d, 69Ah
0x18001cb9f  jmp     loc_18001CB1A
0x18001cba4  mov     rcx, [rdi]
0x18001cba7  mov     rax, [rcx]
0x18001cbaa  mov     r8, rsi
0x18001cbad  lea     rdx, _GUID_ac4530f6_68f2_48b7_803c_647212e1e4be
0x18001cbb4  mov     rax, [rax]
0x18001cbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbbc  mov     ebx, eax
0x18001cbbe  test    eax, eax
0x18001cbc0  jns     short loc_18001CBE3
0x18001cbc2  cmp     eax, 8007000Eh
0x18001cbc7  jnz     short loc_18001CBD1
0x18001cbc9  xor     ecx, ecx; FailedAllocationSize
0x18001cbcb  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x18001cbd1  mov     rdx, [rsp+38h]; unsigned __int64
0x18001cbd6  mov     r8d, 69Dh; unsigned __int64
0x18001cbdc  mov     ecx, ebx; int
0x18001cbde  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18001cbe3  mov     eax, ebx
0x18001cbe5  mov     rbx, [rsp+38h+arg_0]
0x18001cbea  mov     rsi, [rsp+38h+arg_18]
0x18001cbef  add     rsp, 30h
0x18001cbf3  pop     rdi
0x18001cbf4  retn
```
