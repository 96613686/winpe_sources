# FwppDeepCopyFromVerIndependent_FWPM_FILTER0

- ea: `0x18005de0c`
- end: `0x18005e027`
- name: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800598a4`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180018660`
- `0x180059b64`
- `0x18005bf80`
- `0x18005db8c`
- `0x18005dd70`
- `0x18005de0c`
- `0x18005e550`
- `0x18005e7b8`
- `0x180061318`
- `0x1800644f8`

## string_xrefs

- `0x18005df59`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS`
- `0x18005df71`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS`
- `0x18005df8d`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`
- `0x18005e019`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_FILTER0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // rcx
  __int64 v15; // rax

  if ( !a1 || !a2 )
  {
    v15 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyFromVerIndependent_FWPM_FILTER0", 3223453724LL);
LABEL_31:
    v4 = v15;
    if ( !v15 )
      return v4;
    goto LABEL_22;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyFromVerIndependent_GUID)();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
    if ( !v4 )
    {
      v6 = (_DWORD *)(a1 + 32);
      if ( a1 == -32 || (v5 = (_DWORD *)(a2 + 32), a2 == -32) )
      {
        v12 = WfpReportAppErrorAsNtStatus(
                (__int64)v5,
                (__int64)"FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS",
                3223453724LL);
        v4 = v12;
        if ( v12 )
        {
          WfpReportError(v12, (int)"FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS");
          goto LABEL_22;
        }
      }
      else
      {
        *v5 = *v6;
      }
      v7 = *(_QWORD *)(a1 + 40);
      if ( v7 )
      {
        v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v7, a2 + 40);
        if ( v4 )
          goto LABEL_22;
      }
      v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1 + 48, a2 + 48);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_GUID(a1 + 64, a2 + 64);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_GUID(a1 + 80, a2 + 80);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_FWP_VALUE0(a1 + 96, a2 + 96);
      if ( v4 )
        goto LABEL_22;
      v8 = *(_QWORD *)(a1 + 120);
      if ( v8 )
      {
        v4 = FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0(v8, *(unsigned int *)(a1 + 112), a2 + 120);
        if ( v4 )
          goto LABEL_22;
        *(_DWORD *)(a2 + 112) = *(_DWORD *)(a1 + 112);
      }
      v4 = FwppDeepCopyFromVerIndependent_FWPM_ACTION0(a1 + 128, a2 + 128);
      if ( !v4 )
      {
        v9 = a2 + 152;
        v10 = a1 + 152;
        v11 = (*v6 & 4) != 0
            ? FwppDeepCopyFromVerIndependent_GUID(v10, v9)
            : FwppDeepCopyFromVerIndependent_UINT64(v10, v9);
        v4 = v11;
        if ( !v11 )
        {
          v14 = *(_QWORD *)(a1 + 168);
          if ( !v14 || (v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v14, a2 + 168)) == 0 )
          {
            v4 = FwppDeepCopyFromVerIndependent_UINT64(a1 + 176, a2 + 176);
            if ( !v4 )
            {
              v15 = FwppDeepCopyFromVerIndependent_FWP_VALUE0(a1 + 184, a2 + 184);
              goto LABEL_31;
            }
          }
        }
      }
    }
  }
LABEL_22:
  FwppDeepFreeContentsOnly_FWPM_FILTER0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_FWPM_FILTER0");
  return v4;
}

```

## disassembly

```asm
0x18005de0c  push    rbx
0x18005de0e  push    rsi
0x18005de0f  push    rdi
0x18005de10  push    r14
0x18005de12  sub     rsp, 38h
0x18005de16  mov     rsi, rdx
0x18005de19  mov     rdi, rcx
0x18005de1c  test    rcx, rcx
0x18005de1f  jz      loc_18005E013
0x18005de25  test    rdx, rdx
0x18005de28  jz      loc_18005E013
0x18005de2e  call    FwppDeepCopyFromVerIndependent_GUID
0x18005de33  mov     rbx, rax
0x18005de36  test    rax, rax
0x18005de39  jnz     loc_18005DF80
0x18005de3f  lea     rdx, [rsi+10h]
0x18005de43  lea     rcx, [rdi+10h]
0x18005de47  call    FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0
0x18005de4c  mov     rbx, rax
0x18005de4f  test    rax, rax
0x18005de52  jnz     loc_18005DF80
0x18005de58  lea     r14, [rdi+20h]
0x18005de5c  test    r14, r14
0x18005de5f  jz      loc_18005DF53
0x18005de65  lea     rcx, [rsi+20h]
0x18005de69  test    rcx, rcx
0x18005de6c  jz      loc_18005DF53
0x18005de72  mov     eax, [r14]
0x18005de75  mov     [rcx], eax
0x18005de77  mov     rcx, [rdi+28h]
0x18005de7b  test    rcx, rcx
0x18005de7e  jz      short loc_18005DE95
0x18005de80  lea     rdx, [rsi+28h]
0x18005de84  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x18005de89  mov     rbx, rax
0x18005de8c  test    rax, rax
0x18005de8f  jnz     loc_18005DF80
0x18005de95  lea     rdx, [rsi+30h]
0x18005de99  lea     rcx, [rdi+30h]
0x18005de9d  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18005dea2  mov     rbx, rax
0x18005dea5  test    rax, rax
0x18005dea8  jnz     loc_18005DF80
0x18005deae  lea     rdx, [rsi+40h]
0x18005deb2  lea     rcx, [rdi+40h]
0x18005deb6  call    FwppDeepCopyFromVerIndependent_GUID
0x18005debb  mov     rbx, rax
0x18005debe  test    rax, rax
0x18005dec1  jnz     loc_18005DF80
0x18005dec7  lea     rdx, [rsi+50h]
0x18005decb  lea     rcx, [rdi+50h]
0x18005decf  call    FwppDeepCopyFromVerIndependent_GUID
0x18005ded4  mov     rbx, rax
0x18005ded7  test    rax, rax
0x18005deda  jnz     loc_18005DF80
0x18005dee0  lea     rdx, [rsi+60h]
0x18005dee4  lea     rcx, [rdi+60h]
0x18005dee8  call    FwppDeepCopyFromVerIndependent_FWP_VALUE0
0x18005deed  mov     rbx, rax
0x18005def0  test    rax, rax
0x18005def3  jnz     loc_18005DF80
0x18005def9  mov     rcx, [rdi+78h]
0x18005defd  test    rcx, rcx
0x18005df00  jz      short loc_18005DF1C
0x18005df02  mov     edx, [rdi+70h]
0x18005df05  lea     r8, [rsi+78h]
0x18005df09  call    FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0
0x18005df0e  mov     rbx, rax
0x18005df11  test    rax, rax
0x18005df14  jnz     short loc_18005DF80
0x18005df16  mov     eax, [rdi+70h]
0x18005df19  mov     [rsi+70h], eax
0x18005df1c  lea     rdx, [rsi+80h]
0x18005df23  lea     rcx, [rdi+80h]
0x18005df2a  call    FwppDeepCopyFromVerIndependent_FWPM_ACTION0
0x18005df2f  mov     rbx, rax
0x18005df32  test    rax, rax
0x18005df35  jnz     short loc_18005DF80
0x18005df37  mov     eax, [r14]
0x18005df3a  lea     rdx, [rsi+98h]
0x18005df41  lea     rcx, [rdi+98h]
0x18005df48  test    al, 4
0x18005df4a  jz      short loc_18005DFAA
0x18005df4c  call    FwppDeepCopyFromVerIndependent_GUID
0x18005df51  jmp     short loc_18005DFAF
0x18005df53  mov     r8d, 0C022001Ch
0x18005df59  lea     rdx, aFwppdeepcopyfr_82; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x18005df60  call    WfpReportAppErrorAsNtStatus
0x18005df65  mov     rbx, rax
0x18005df68  test    rax, rax
0x18005df6b  jz      loc_18005DE77
0x18005df71  lea     rdx, aFwppdeepcopyfr_82; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x18005df78  mov     rcx, rax
0x18005df7b  call    WfpReportError
0x18005df80  mov     rcx, rsi
0x18005df83  call    FwppDeepFreeContentsOnly_FWPM_FILTER0
0x18005df88  test    rbx, rbx
0x18005df8b  jz      short loc_18005DF9C
0x18005df8d  lea     rdx, aFwppdeepcopyfr_89; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x18005df94  mov     rcx, rbx
0x18005df97  call    WfpReportError
0x18005df9c  mov     rax, rbx
0x18005df9f  add     rsp, 38h
0x18005dfa3  pop     r14
0x18005dfa5  pop     rdi
0x18005dfa6  pop     rsi
0x18005dfa7  pop     rbx
0x18005dfa8  retn
0x18005dfaa  call    FwppDeepCopyFromVerIndependent_UINT64
0x18005dfaf  mov     rbx, rax
0x18005dfb2  test    rax, rax
0x18005dfb5  jnz     short loc_18005DF80
0x18005dfb7  mov     rcx, [rdi+0A8h]
0x18005dfbe  test    rcx, rcx
0x18005dfc1  jz      short loc_18005DFD7
0x18005dfc3  lea     rdx, [rsi+0A8h]
0x18005dfca  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x18005dfcf  mov     rbx, rax
0x18005dfd2  test    rax, rax
0x18005dfd5  jnz     short loc_18005DF80
0x18005dfd7  lea     rdx, [rsi+0B0h]
0x18005dfde  lea     rcx, [rdi+0B0h]
0x18005dfe5  call    FwppDeepCopyFromVerIndependent_UINT64
0x18005dfea  mov     rbx, rax
0x18005dfed  test    rax, rax
0x18005dff0  jnz     short loc_18005DF80
0x18005dff2  lea     rdx, [rsi+0B8h]
0x18005dff9  lea     rcx, [rdi+0B8h]
0x18005e000  call    FwppDeepCopyFromVerIndependent_FWP_VALUE0
0x18005e005  mov     rbx, rax
0x18005e008  test    rax, rax
0x18005e00b  jnz     loc_18005DF80
0x18005e011  jmp     short loc_18005DF9C
0x18005e013  mov     r8d, 0C022001Ch
0x18005e019  lea     rdx, aFwppdeepcopyfr_89; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x18005e020  call    WfpReportAppErrorAsNtStatus
0x18005e025  jmp     short loc_18005E005
```
