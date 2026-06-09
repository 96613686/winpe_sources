# CIVIAudioInPin::GetParameterValues(_GUID const *,tagVARIANT * *,ulong *)

- ea: `0x18001dce0`
- end: `0x18001deb5`
- name: `?GetParameterValues@CIVIAudioInPin@@UEAAJPEBU_GUID@@PEAPEAUtagVARIANT@@PEAK@Z`
- size: `469`
- prototype: `int(CIVIAudioInPin *__hidden this, const struct _GUID *, struct tagVARIANT **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001dce0`
- `0x18001dec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ddc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ddc9`

## pseudocode

```c
__int64 __fastcall CIVIAudioInPin::GetParameterValues(
        CIVIAudioInPin *this,
        const struct _GUID *a2,
        struct tagVARIANT **a3,
        unsigned int *a4)
{
  struct tagVARIANT *v7; // rax

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data4 )
  {
    return 2147746576LL;
  }
  *a3 = 0;
  *a4 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_e5005239_bd89_4be3_9c0f_5dde317988cc )
    return CIVIAudioInPin::GetParameterValues_AVDecCommonInputFormat(this, a3, a4);
  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data1
    || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data4 )
  {
    return 1;
  }
  v7 = (struct tagVARIANT *)CoTaskMemAlloc(0xF0u);
  if ( !v7 )
    return 2147942414LL;
  v7->lVal = 16000;
  v7->vt = 19;
  v7[1].vt = 19;
  v7[2].vt = 19;
  v7[3].vt = 19;
  v7[4].vt = 19;
  v7[5].vt = 19;
  v7[6].vt = 19;
  v7[7].vt = 19;
  v7[8].vt = 19;
  v7[9].vt = 19;
  v7[1].lVal = 22050;
  v7[2].lVal = 24000;
  v7[3].lVal = 32000;
  v7[4].lVal = 44100;
  v7[5].lVal = 48000;
  v7[6].lVal = 88200;
  v7[7].lVal = 96000;
  v7[8].lVal = 176400;
  v7[9].lVal = 192000;
  *a4 = 10;
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x18001dce0  mov     [rsp+arg_0], rbx
0x18001dce5  push    rdi
0x18001dce6  sub     rsp, 20h
0x18001dcea  mov     rbx, r9
0x18001dced  mov     rdi, r8
0x18001dcf0  test    rdx, rdx
0x18001dcf3  jz      loc_18001DEA4
0x18001dcf9  test    r8, r8
0x18001dcfc  jz      loc_18001DEA4
0x18001dd02  test    rbx, rbx
0x18001dd05  jz      loc_18001DEA4
0x18001dd0b  mov     rax, [rdx]
0x18001dd0e  cmp     rax, qword ptr cs:_GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data1
0x18001dd15  jnz     short loc_18001DD24
0x18001dd17  mov     rax, [rdx+8]
0x18001dd1b  cmp     rax, qword ptr cs:_GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data4
0x18001dd22  jz      short loc_18001DD56
0x18001dd24  mov     rax, [rdx]
0x18001dd27  cmp     rax, qword ptr cs:_GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data1
0x18001dd2e  jnz     short loc_18001DD3D
0x18001dd30  mov     rax, [rdx+8]
0x18001dd34  cmp     rax, qword ptr cs:_GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f.Data4
0x18001dd3b  jz      short loc_18001DD56
0x18001dd3d  mov     rax, [rdx]
0x18001dd40  cmp     rax, qword ptr cs:_GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data1
0x18001dd47  jnz     short loc_18001DD67
0x18001dd49  mov     rax, [rdx+8]
0x18001dd4d  cmp     rax, qword ptr cs:_GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data4
0x18001dd54  jnz     short loc_18001DD67
0x18001dd56  mov     eax, 80040310h
0x18001dd5b  mov     rbx, [rsp+28h+arg_0]
0x18001dd60  add     rsp, 20h
0x18001dd64  pop     rdi
0x18001dd65  retn
0x18001dd67  mov     qword ptr [r8], 0
0x18001dd6e  mov     dword ptr [r9], 0
0x18001dd75  mov     rax, [rdx]
0x18001dd78  cmp     rax, qword ptr cs:_GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data1
0x18001dd7f  jnz     short loc_18001DDA3
0x18001dd81  mov     rax, [rdx+8]
0x18001dd85  cmp     rax, qword ptr cs:_GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data4
0x18001dd8c  jnz     short loc_18001DDA3
0x18001dd8e  mov     r8, rbx; unsigned int *
0x18001dd91  mov     rdx, rdi; struct tagVARIANT **
0x18001dd94  mov     rbx, [rsp+28h+arg_0]
0x18001dd99  add     rsp, 20h
0x18001dd9d  pop     rdi
0x18001dd9e  jmp     ?GetParameterValues_AVDecCommonInputFormat@CIVIAudioInPin@@AEAAJPEAPEAUtagVARIANT@@PEAK@Z; CIVIAudioInPin::GetParameterValues_AVDecCommonInputFormat(tagVARIANT * *,ulong *)
0x18001dda3  mov     rax, [rdx]
0x18001dda6  cmp     rax, qword ptr cs:_GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data1
0x18001ddad  jnz     loc_18001DE93
0x18001ddb3  mov     rax, [rdx+8]
0x18001ddb7  cmp     rax, qword ptr cs:_GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data4
0x18001ddbe  jnz     loc_18001DE93
0x18001ddc4  mov     ecx, 0F0h; cb
0x18001ddc9  call    cs:__imp_CoTaskMemAlloc
0x18001ddd0  nop     dword ptr [rax+rax+00h]
0x18001ddd5  test    rax, rax
0x18001ddd8  jnz     short loc_18001DDED
0x18001ddda  mov     ecx, 8007000Eh
0x18001dddf  mov     eax, ecx
0x18001dde1  mov     rbx, [rsp+28h+arg_0]
0x18001dde6  add     rsp, 20h
0x18001ddea  pop     rdi
0x18001ddeb  retn
0x18001dded  mov     edx, 13h
0x18001ddf2  mov     dword ptr [rax+8], 3E80h
0x18001ddf9  mov     [rax], dx
0x18001ddfc  xor     ecx, ecx
0x18001ddfe  mov     [rax+18h], dx
0x18001de02  mov     [rax+30h], dx
0x18001de06  mov     [rax+48h], dx
0x18001de0a  mov     [rax+60h], dx
0x18001de0e  mov     [rax+78h], dx
0x18001de12  mov     [rax+90h], dx
0x18001de19  mov     [rax+0A8h], dx
0x18001de20  mov     [rax+0C0h], dx
0x18001de27  mov     [rax+0D8h], dx
0x18001de2e  mov     dword ptr [rax+20h], 5622h
0x18001de35  mov     dword ptr [rax+38h], 5DC0h
0x18001de3c  mov     dword ptr [rax+50h], 7D00h
0x18001de43  mov     dword ptr [rax+68h], 0AC44h
0x18001de4a  mov     dword ptr [rax+80h], 0BB80h
0x18001de54  mov     dword ptr [rax+98h], 15888h
0x18001de5e  mov     dword ptr [rax+0B0h], 17700h
0x18001de68  mov     dword ptr [rax+0C8h], 2B110h
0x18001de72  mov     dword ptr [rax+0E0h], 2EE00h
0x18001de7c  mov     dword ptr [rbx], 0Ah
0x18001de82  mov     [rdi], rax
0x18001de85  mov     eax, ecx
0x18001de87  mov     rbx, [rsp+28h+arg_0]
0x18001de8c  add     rsp, 20h
0x18001de90  pop     rdi
0x18001de91  retn
0x18001de93  mov     eax, 1
0x18001de98  mov     rbx, [rsp+28h+arg_0]
0x18001de9d  add     rsp, 20h
0x18001dea1  pop     rdi
0x18001dea2  retn
0x18001dea4  mov     rbx, [rsp+28h+arg_0]
0x18001dea9  mov     eax, 80070057h
0x18001deae  add     rsp, 20h
0x18001deb2  pop     rdi
0x18001deb3  retn
```
