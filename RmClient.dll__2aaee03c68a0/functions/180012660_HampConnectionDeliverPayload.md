# HampConnectionDeliverPayload

- ea: `0x180012660`
- end: `0x1800128d6`
- name: `HampConnectionDeliverPayload`
- size: `630`
- prototype: `char __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180012660`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012793`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012884`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012793`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012884`
- `ntdll!RtlFreeHeap` at `0x1800128a9`
- `ntdll!RtlFreeHeap` at `0x1800128a9`

## pseudocode

```c
char __fastcall HampConnectionDeliverPayload(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rdx
  __int128 *v7; // r14
  __int64 v8; // rax
  char v10; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-A5h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v13; // [rsp+50h] [rbp-89h] BYREF
  __int128 v14; // [rsp+60h] [rbp-79h]
  __int128 v15; // [rsp+70h] [rbp-69h]
  __int128 v16; // [rsp+80h] [rbp-59h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-49h] BYREF
  char *v18; // [rsp+A0h] [rbp-39h]
  int v19; // [rsp+A8h] [rbp-31h]
  int v20; // [rsp+ACh] [rbp-2Dh]
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+B0h] [rbp-29h] BYREF
  char *v22; // [rsp+C0h] [rbp-19h]
  int v23; // [rsp+C8h] [rbp-11h]
  int v24; // [rsp+CCh] [rbp-Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+D0h] [rbp-9h]
  __int64 v26; // [rsp+D8h] [rbp-1h]
  char *v27; // [rsp+E0h] [rbp+7h]
  __int64 v28; // [rsp+E8h] [rbp+Fh]

  v4 = a2[7];
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( a3 )
  {
    v7 = (__int128 *)a3;
    *(_QWORD *)(a3 + 8) = v4;
  }
  else
  {
    v7 = &v13;
    *(_QWORD *)&v13 = a2[6];
    *((_QWORD *)&v13 + 1) = v4;
    LODWORD(v14) = 3;
  }
  if ( (unsigned int)dword_18002E038 > 5 && (qword_18002E048 & 1) != 0 && (qword_18002E050 & 1) == qword_18002E050 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_18002E040;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = (unsigned __int16)*off_18002E040;
    v18 = &byte_180026D37;
    UserData.Reserved = 2;
    v19 = 21;
    v20 = 1;
    v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  (*(void (__fastcall **)(__int128 *))(a1 + 80))(v7);
  LOBYTE(v8) = dword_18002E038;
  if ( (unsigned int)dword_18002E038 > 4 )
  {
    LOBYTE(v8) = qword_18002E048;
    if ( (qword_18002E048 & 3) != 0 )
    {
      v8 = qword_18002E050 & 3;
      if ( v8 == qword_18002E050 )
      {
        v10 = *((_BYTE *)v7 + 16);
        *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)v7;
        v28 = 1;
        v27 = &v10;
        p_EventDescriptor = &EventDescriptor;
        v21.Ptr = (ULONGLONG)off_18002E040;
        v26 = 8;
        UserData.Ptr = 0x2040B000000LL;
        *(_QWORD *)&UserData.Size = 3;
        v21.Size = (unsigned __int16)*off_18002E040;
        v22 = byte_180026C93;
        v21.Reserved = 2;
        v23 = 40;
        v24 = 1;
        v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LOBYTE(v8) = EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v21);
      }
    }
  }
  if ( !a3 )
  {
    a2[6] = -1;
    LOBYTE(v8) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a2);
  }
  return v8;
}

```

## disassembly

```asm
0x180012660  mov     [rsp-8+arg_18], rbx
0x180012665  push    rbp
0x180012666  push    rsi
0x180012667  push    rdi
0x180012668  push    r12
0x18001266a  push    r13
0x18001266c  push    r14
0x18001266e  push    r15
0x180012670  lea     rbp, [rsp-27h]
0x180012675  sub     rsp, 100h
0x18001267c  mov     rax, cs:__security_cookie
0x180012683  xor     rax, rsp
0x180012686  mov     [rbp+57h+var_40], rax
0x18001268a  xorps   xmm0, xmm0
0x18001268d  mov     rsi, rdx
0x180012690  mov     rdx, [rdx+38h]
0x180012694  mov     rdi, r8
0x180012697  mov     r13, rcx
0x18001269a  movups  [rsp+130h+var_E0], xmm0
0x18001269f  movups  [rbp+57h+var_D0], xmm0
0x1800126a3  movups  [rbp+57h+var_C0], xmm0
0x1800126a7  movups  [rbp+57h+var_B0], xmm0
0x1800126ab  test    r8, r8
0x1800126ae  jnz     short loc_1800126CC
0x1800126b0  mov     rax, [rsi+30h]
0x1800126b4  lea     r14, [rsp+130h+var_E0]
0x1800126b9  mov     qword ptr [rsp+130h+var_E0], rax
0x1800126be  mov     qword ptr [rsp+130h+var_E0+8], rdx
0x1800126c3  mov     dword ptr [rbp+57h+var_D0], 3
0x1800126ca  jmp     short loc_1800126D3
0x1800126cc  mov     r14, rdi
0x1800126cf  mov     [r8+8], rdx
0x1800126d3  mov     eax, cs:dword_18002E038
0x1800126d9  lea     r15, _TraceLoggingMetadataEnd
0x1800126e0  lea     r12, _TraceLoggingMetadata
0x1800126e7  cmp     eax, 5
0x1800126ea  jbe     loc_180012799
0x1800126f0  mov     rcx, cs:qword_18002E050
0x1800126f7  mov     rax, cs:qword_18002E048
0x1800126fe  test    al, 1
0x180012700  jz      loc_180012799
0x180012706  mov     rax, rcx
0x180012709  and     eax, 1
0x18001270c  cmp     rax, rcx
0x18001270f  jnz     loc_180012799
0x180012715  movzx   eax, cs:word_180026D2D
0x18001271c  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180012721  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180012725  xor     r9d, r9d; RelatedActivityId
0x180012728  mov     rax, cs:off_18002E040
0x18001272f  xor     r8d, r8d; ActivityId
0x180012732  mov     [rbp+57h+var_A0.Ptr], rax
0x180012736  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18001273e  mov     [rsp+130h+EventDescriptor.Keyword], 1
0x180012747  movzx   eax, word ptr [rax]
0x18001274a  mov     [rbp+57h+var_A0.Size], eax
0x18001274d  lea     rax, byte_180026D37
0x180012754  mov     [rbp+57h+var_90], rax
0x180012758  mov     rax, r15
0x18001275b  sub     eax, r12d
0x18001275e  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x180012765  mov     [rbp+57h+var_88], 15h
0x18001276c  mov     [rbp+57h+var_84], 1
0x180012773  mov     [rsp+130h+var_FC], eax
0x180012777  mov     eax, [rsp+130h+var_FC]
0x18001277b  mov     rcx, cs:RegHandle; RegHandle
0x180012782  lea     rax, [rbp+57h+var_A0]
0x180012786  mov     [rsp+130h+UserData], rax; UserData
0x18001278b  mov     [rsp+130h+UserDataCount], 2; UserDataCount
0x180012793  call    cs:__imp_EventWriteTransfer
0x180012799  mov     rax, [r13+50h]
0x18001279d  mov     rcx, r14
0x1800127a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a5  mov     eax, cs:dword_18002E038
0x1800127ab  cmp     eax, 4
0x1800127ae  jbe     loc_18001288A
0x1800127b4  mov     rcx, cs:qword_18002E050
0x1800127bb  mov     rax, cs:qword_18002E048
0x1800127c2  test    al, 3
0x1800127c4  jz      loc_18001288A
0x1800127ca  mov     rax, rcx
0x1800127cd  and     eax, 3
0x1800127d0  cmp     rax, rcx
0x1800127d3  jnz     loc_18001288A
0x1800127d9  movzx   eax, byte ptr [r14+10h]
0x1800127de  lea     rdx, [rbp+57h+var_A0]; EventDescriptor
0x1800127e2  mov     [rsp+130h+var_100], al
0x1800127e6  sub     r15d, r12d
0x1800127e9  mov     rax, [r14]
0x1800127ec  xor     r9d, r9d; RelatedActivityId
0x1800127ef  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1800127f4  xor     r8d, r8d; ActivityId
0x1800127f7  mov     [rbp+57h+var_48], 1
0x1800127ff  lea     rax, [rsp+130h+var_100]
0x180012804  mov     [rbp+57h+var_50], rax
0x180012808  lea     rax, [rsp+130h+EventDescriptor]
0x18001280d  mov     [rbp+57h+var_60], rax
0x180012811  movzx   eax, cs:word_180026C89
0x180012818  mov     dword ptr [rbp+57h+var_A0.Ptr+4], eax
0x18001281b  mov     rax, cs:off_18002E040
0x180012822  mov     [rbp+57h+var_80.Ptr], rax
0x180012826  mov     [rbp+57h+var_58], 8
0x18001282e  mov     dword ptr [rbp+57h+var_A0.Ptr], 0B000000h
0x180012835  mov     qword ptr [rbp+57h+var_A0.Size], 3
0x18001283d  movzx   eax, word ptr [rax]
0x180012840  mov     [rbp+57h+var_80.Size], eax
0x180012843  lea     rax, byte_180026C93
0x18001284a  mov     [rbp+57h+var_70], rax
0x18001284e  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180012855  mov     [rbp+57h+var_68], 28h ; '('
0x18001285c  mov     [rbp+57h+var_64], 1
0x180012863  mov     [rsp+130h+var_FC], r15d
0x180012868  mov     eax, [rsp+130h+var_FC]
0x18001286c  mov     rcx, cs:RegHandle; RegHandle
0x180012873  lea     rax, [rbp+57h+var_80]
0x180012877  mov     [rsp+130h+UserData], rax; UserData
0x18001287c  mov     [rsp+130h+UserDataCount], 4; UserDataCount
0x180012884  call    cs:__imp_EventWriteTransfer
0x18001288a  test    rdi, rdi
0x18001288d  jnz     short loc_1800128AF
0x18001288f  mov     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x180012897  mov     r8, rsi; P
0x18001289a  mov     rcx, gs:60h
0x1800128a3  xor     edx, edx; Flags
0x1800128a5  mov     rcx, [rcx+30h]; HeapHandle
0x1800128a9  call    cs:__imp_RtlFreeHeap
0x1800128af  mov     rcx, [rbp+57h+var_40]
0x1800128b3  xor     rcx, rsp; StackCookie
0x1800128b6  call    __security_check_cookie
0x1800128bb  mov     rbx, [rsp+130h+arg_18]
0x1800128c3  add     rsp, 100h
0x1800128ca  pop     r15
0x1800128cc  pop     r14
0x1800128ce  pop     r13
0x1800128d0  pop     r12
0x1800128d2  pop     rdi
0x1800128d3  pop     rsi
0x1800128d4  pop     rbp
0x1800128d5  retn
```
