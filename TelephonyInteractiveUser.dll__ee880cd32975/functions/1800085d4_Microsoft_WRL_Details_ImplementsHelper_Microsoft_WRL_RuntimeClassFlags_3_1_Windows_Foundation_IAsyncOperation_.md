# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x1800085d4`
- end: `0x1800086c5`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@_N@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de30`

## callees

- `0x1800085d4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  if ( *a2 == -843714637
    && a2[1] == *(_DWORD *)&GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data2
    && a2[2] == *(_DWORD *)GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4
    && a2[3] == *(_DWORD *)&GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4[4] )
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
0x1800085d4  cmp     dword ptr [rdx], 0CDB5EFB3h
0x1800085da  jnz     short loc_1800085FD
0x1800085dc  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data2
0x1800085e2  cmp     [rdx+4], eax
0x1800085e5  jnz     short loc_1800085FD
0x1800085e7  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4
0x1800085ed  cmp     [rdx+8], eax
0x1800085f0  jnz     short loc_1800085FD
0x1800085f2  mov     eax, dword ptr cs:_GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a.Data4+4
0x1800085f8  cmp     [rdx+0Ch], eax
0x1800085fb  jz      short loc_18000862A
0x1800085fd  add     rcx, 8
0x180008601  cmp     dword ptr [rdx], 7A900AF8h
0x180008607  jnz     short loc_180008630
0x180008609  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x18000860f  cmp     [rdx+4], eax
0x180008612  jnz     short loc_180008630
0x180008614  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x18000861a  cmp     [rdx+8], eax
0x18000861d  jnz     short loc_180008630
0x18000861f  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x180008625  cmp     [rdx+0Ch], eax
0x180008628  jnz     short loc_180008630
0x18000862a  mov     [r8], rcx
0x18000862d  xor     eax, eax
0x18000862f  retn
0x180008630  add     rcx, 8
0x180008634  cmp     dword ptr [rdx], 5FB52445h
0x18000863a  jnz     short loc_18000865D
0x18000863c  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x180008642  cmp     [rdx+4], eax
0x180008645  jnz     short loc_18000865D
0x180008647  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x18000864d  cmp     [rdx+8], eax
0x180008650  jnz     short loc_18000865D
0x180008652  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x180008658  cmp     [rdx+0Ch], eax
0x18000865b  jz      short loc_18000862A
0x18000865d  add     rcx, 8
0x180008661  cmp     dword ptr [rdx], 47CFCC0Eh
0x180008667  jnz     short loc_180008690
0x180008669  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x18000866f  cmp     [rdx+4], eax
0x180008672  jnz     short loc_18000868A
0x180008674  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x18000867a  cmp     [rdx+8], eax
0x18000867d  jnz     short loc_18000868A
0x18000867f  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x180008685  cmp     [rdx+0Ch], eax
0x180008688  jz      short loc_18000862A
0x18000868a  mov     eax, 80004002h
0x18000868f  retn
0x180008690  cmp     dword ptr [rdx], 19874D36h
0x180008696  jnz     short loc_18000868A
0x180008698  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x18000869e  cmp     [rdx+4], eax
0x1800086a1  jnz     short loc_18000868A
0x1800086a3  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x1800086a9  cmp     [rdx+8], eax
0x1800086ac  jnz     short loc_18000868A
0x1800086ae  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x1800086b4  cmp     [rdx+0Ch], eax
0x1800086b7  jnz     short loc_18000868A
0x1800086b9  lea     rax, [rcx+8]
0x1800086bd  mov     [r8], rax
0x1800086c0  jmp     loc_18000862D
```
