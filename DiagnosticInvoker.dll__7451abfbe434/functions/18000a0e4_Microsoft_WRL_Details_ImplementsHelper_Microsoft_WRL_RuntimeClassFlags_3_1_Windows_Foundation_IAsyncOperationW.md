# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x18000a0e4`
- end: `0x18000a1d5`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d280`

## callees

- `0x18000a0e4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  if ( *a2 == -1151514306
    && a2[1] == *(_DWORD *)&GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data2
    && a2[2] == *(_DWORD *)GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data4
    && a2[3] == *(_DWORD *)&GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data4[4] )
  {
    goto LABEL_9;
  }
  a1 += 8;
  if ( *a2 == 2056260344
    && a2[1] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
    && a2[2] == *(_DWORD *)GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
    && a2[3] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4[4] )
  {
    goto LABEL_9;
  }
  a1 += 8;
  if ( *a2 == 1605706821
    && a2[1] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
    && a2[2] == *(_DWORD *)GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
    && a2[3] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4[4] )
  {
    goto LABEL_9;
  }
  a1 += 8;
  if ( *a2 != 1204800526 )
  {
    if ( *a2 != 428297526
      || a2[1] != *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
      || a2[2] != *(_DWORD *)GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
      || a2[3] != *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4[4] )
    {
      return 2147500034LL;
    }
    *a3 = a1 + 8;
    return 0;
  }
  if ( a2[1] == *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
    && a2[2] == *(_DWORD *)GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
    && a2[3] == *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4[4] )
  {
LABEL_9:
    *a3 = a1;
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000a0e4  cmp     dword ptr [rdx], 0BB5D493Eh
0x18000a0ea  jnz     short loc_18000A10D
0x18000a0ec  mov     eax, dword ptr cs:_GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data2
0x18000a0f2  cmp     [rdx+4], eax
0x18000a0f5  jnz     short loc_18000A10D
0x18000a0f7  mov     eax, dword ptr cs:_GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data4
0x18000a0fd  cmp     [rdx+8], eax
0x18000a100  jnz     short loc_18000A10D
0x18000a102  mov     eax, dword ptr cs:_GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data4+4
0x18000a108  cmp     [rdx+0Ch], eax
0x18000a10b  jz      short loc_18000A13A
0x18000a10d  add     rcx, 8
0x18000a111  cmp     dword ptr [rdx], 7A900AF8h
0x18000a117  jnz     short loc_18000A140
0x18000a119  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x18000a11f  cmp     [rdx+4], eax
0x18000a122  jnz     short loc_18000A140
0x18000a124  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x18000a12a  cmp     [rdx+8], eax
0x18000a12d  jnz     short loc_18000A140
0x18000a12f  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x18000a135  cmp     [rdx+0Ch], eax
0x18000a138  jnz     short loc_18000A140
0x18000a13a  mov     [r8], rcx
0x18000a13d  xor     eax, eax
0x18000a13f  retn
0x18000a140  add     rcx, 8
0x18000a144  cmp     dword ptr [rdx], 5FB52445h
0x18000a14a  jnz     short loc_18000A16D
0x18000a14c  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x18000a152  cmp     [rdx+4], eax
0x18000a155  jnz     short loc_18000A16D
0x18000a157  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x18000a15d  cmp     [rdx+8], eax
0x18000a160  jnz     short loc_18000A16D
0x18000a162  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x18000a168  cmp     [rdx+0Ch], eax
0x18000a16b  jz      short loc_18000A13A
0x18000a16d  add     rcx, 8
0x18000a171  cmp     dword ptr [rdx], 47CFCC0Eh
0x18000a177  jnz     short loc_18000A1A0
0x18000a179  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x18000a17f  cmp     [rdx+4], eax
0x18000a182  jnz     short loc_18000A19A
0x18000a184  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x18000a18a  cmp     [rdx+8], eax
0x18000a18d  jnz     short loc_18000A19A
0x18000a18f  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x18000a195  cmp     [rdx+0Ch], eax
0x18000a198  jz      short loc_18000A13A
0x18000a19a  mov     eax, 80004002h
0x18000a19f  retn
0x18000a1a0  cmp     dword ptr [rdx], 19874D36h
0x18000a1a6  jnz     short loc_18000A19A
0x18000a1a8  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x18000a1ae  cmp     [rdx+4], eax
0x18000a1b1  jnz     short loc_18000A19A
0x18000a1b3  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x18000a1b9  cmp     [rdx+8], eax
0x18000a1bc  jnz     short loc_18000A19A
0x18000a1be  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x18000a1c4  cmp     [rdx+0Ch], eax
0x18000a1c7  jnz     short loc_18000A19A
0x18000a1c9  lea     rax, [rcx+8]
0x18000a1cd  mov     [r8], rax
0x18000a1d0  jmp     loc_18000A13D
```
