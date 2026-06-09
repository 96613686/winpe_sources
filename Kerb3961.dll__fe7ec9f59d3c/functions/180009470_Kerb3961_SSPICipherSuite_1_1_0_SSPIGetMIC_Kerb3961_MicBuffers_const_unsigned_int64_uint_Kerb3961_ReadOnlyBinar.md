# Kerb3961::SSPICipherSuite<1,1,0>::SSPIGetMIC(Kerb3961::MicBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180009470`
- end: `0x18000959e`
- name: `?SSPIGetMIC@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@_KIAEBUReadOnlyBinary@2@_N3@Z`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180004e74`
- `0x180009470`
- `0x18001e010`

## string_xrefs

- `0x1800094d9`: `combinedBuffer`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::SSPIGetMIC(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7,
        char a8)
{
  const char *v12; // rdx
  int v13; // r8d
  int v14; // esi
  _QWORD *v15; // r8
  _BYTE v17[8]; // [rsp+50h] [rbp-58h] BYREF
  void *v18; // [rsp+58h] [rbp-50h]
  char *v19; // [rsp+60h] [rbp-48h]

  if ( a5 == -2147483647 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"QOP != KERB_WRAP_NO_ENCRYPT",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893046;
  }
  else
  {
    Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(v17, a3);
    v14 = (int)v19;
    if ( (int)v19 >= 0 )
    {
      if ( (_DWORD)v19 == 255 )
        v15 = *(_QWORD **)(a3 + 8);
      else
        v15 = v17;
      if ( *v15 <= 0xFFFFFFFFFFFF0000uLL )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD *, __int64, int, __int64, char, char))(*(_QWORD *)a1 + 328LL))(
          a1,
          a2,
          v15,
          a4,
          a5,
          a6,
          a7,
          a8);
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"effectiveInput.length <= MessageLimit",
          v12);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -1073741675;
      }
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"combinedBuffer",
        (const char *)(unsigned int)v19,
        v13);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
    }
    if ( v18 )
      operator delete(v18, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x180009470  push    rbx
0x180009472  push    rbp
0x180009473  push    rsi
0x180009474  push    r12
0x180009476  push    r14
0x180009478  push    r15
0x18000947a  sub     rsp, 78h
0x18000947e  mov     r14d, [rsp+0A8h+arg_20]
0x180009486  mov     r12, r9
0x180009489  mov     rbp, r8
0x18000948c  mov     rbx, rdx
0x18000948f  mov     r15, rcx
0x180009492  cmp     r14d, 80000001h
0x180009499  jnz     short loc_1800094C2
0x18000949b  lea     rcx, aQopKerbWrapNoE; "QOP != KERB_WRAP_NO_ENCRYPT"
0x1800094a2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800094a7  mov     qword ptr [rbx], 0
0x1800094ae  mov     qword ptr [rbx+8], 0
0x1800094b6  mov     dword ptr [rbx+10h], 8009030Ah
0x1800094bd  jmp     loc_18000958D
0x1800094c2  mov     rdx, rbp
0x1800094c5  lea     rcx, [rsp+0A8h+var_58]
0x1800094ca  call    ?CoalesceMICBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(Kerb3961::MicBuffers const &)
0x1800094cf  mov     esi, dword ptr [rsp+0A8h+var_48]
0x1800094d3  test    esi, esi
0x1800094d5  jns     short loc_1800094FC
0x1800094d7  mov     edx, esi; char *
0x1800094d9  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800094e0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800094e5  mov     qword ptr [rbx], 0
0x1800094ec  mov     qword ptr [rbx+8], 0
0x1800094f4  mov     [rbx+10h], esi
0x1800094f7  jmp     loc_18000957C
0x1800094fc  cmp     esi, 0FFh
0x180009502  jnz     short loc_18000950A
0x180009504  mov     r8, [rbp+8]
0x180009508  jmp     short loc_18000950F
0x18000950a  lea     r8, [rsp+0A8h+var_58]
0x18000950f  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180009516  jbe     short loc_18000953C
0x180009518  lea     rcx, aEffectiveinput; "effectiveInput.length <= MessageLimit"
0x18000951f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009524  mov     qword ptr [rbx], 0
0x18000952b  mov     qword ptr [rbx+8], 0
0x180009533  mov     dword ptr [rbx+10h], 0C0000095h
0x18000953a  jmp     short loc_18000957C
0x18000953c  mov     cl, [rsp+0A8h+arg_38]
0x180009543  mov     r9, r12
0x180009546  mov     rax, [r15]
0x180009549  mov     rdx, rbx
0x18000954c  mov     [rsp+0A8h+var_70], cl
0x180009550  mov     cl, [rsp+0A8h+arg_30]
0x180009557  mov     [rsp+0A8h+var_78], cl
0x18000955b  mov     rcx, [rsp+0A8h+arg_28]
0x180009563  mov     rax, [rax+148h]
0x18000956a  mov     [rsp+0A8h+var_80], rcx
0x18000956f  mov     rcx, r15
0x180009572  mov     [rsp+0A8h+var_88], r14d
0x180009577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957c  mov     rcx, [rsp+0A8h+var_50]; void *
0x180009581  test    rcx, rcx
0x180009584  jz      short loc_18000958D
0x180009586  xor     edx, edx; struct std::nothrow_t *
0x180009588  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000958d  mov     rax, rbx
0x180009590  add     rsp, 78h
0x180009594  pop     r15
0x180009596  pop     r14
0x180009598  pop     r12
0x18000959a  pop     rsi
0x18000959b  pop     rbp
0x18000959c  pop     rbx
0x18000959d  retn
```
