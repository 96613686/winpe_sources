# Kerb3961::SSPICipherSuite<1,1,0>::SSPIGetMIC(Kerb3961::MicBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180005fb0`
- end: `0x1800060dd`
- name: `?SSPIGetMIC@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@_KIAEBUReadOnlyBinary@2@_N3@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002174`
- `0x180005fb0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180006019`: `combinedBuffer`

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
  __int64 v18; // [rsp+58h] [rbp-50h]
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
      Kerb3961Free(v18);
  }
  return a2;
}

```

## disassembly

```asm
0x180005fb0  push    rbx
0x180005fb2  push    rbp
0x180005fb3  push    rsi
0x180005fb4  push    r12
0x180005fb6  push    r14
0x180005fb8  push    r15
0x180005fba  sub     rsp, 78h
0x180005fbe  mov     r14d, [rsp+0A8h+arg_20]
0x180005fc6  mov     r12, r9
0x180005fc9  mov     rbp, r8
0x180005fcc  mov     rbx, rdx
0x180005fcf  mov     r15, rcx
0x180005fd2  cmp     r14d, 80000001h
0x180005fd9  jnz     short loc_180006002
0x180005fdb  lea     rcx, aQopKerbWrapNoE; "QOP != KERB_WRAP_NO_ENCRYPT"
0x180005fe2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005fe7  mov     qword ptr [rbx], 0
0x180005fee  mov     qword ptr [rbx+8], 0
0x180005ff6  mov     dword ptr [rbx+10h], 8009030Ah
0x180005ffd  jmp     loc_1800060CB
0x180006002  mov     rdx, rbp
0x180006005  lea     rcx, [rsp+0A8h+var_58]
0x18000600a  call    ?CoalesceMICBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMicBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceMICBuffers(Kerb3961::MicBuffers const &)
0x18000600f  mov     esi, dword ptr [rsp+0A8h+var_48]
0x180006013  test    esi, esi
0x180006015  jns     short loc_18000603C
0x180006017  mov     edx, esi; char *
0x180006019  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180006020  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006025  mov     qword ptr [rbx], 0
0x18000602c  mov     qword ptr [rbx+8], 0
0x180006034  mov     [rbx+10h], esi
0x180006037  jmp     loc_1800060BC
0x18000603c  cmp     esi, 0FFh
0x180006042  jnz     short loc_18000604A
0x180006044  mov     r8, [rbp+8]
0x180006048  jmp     short loc_18000604F
0x18000604a  lea     r8, [rsp+0A8h+var_58]
0x18000604f  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180006056  jbe     short loc_18000607C
0x180006058  lea     rcx, aEffectiveinput; "effectiveInput.length <= MessageLimit"
0x18000605f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006064  mov     qword ptr [rbx], 0
0x18000606b  mov     qword ptr [rbx+8], 0
0x180006073  mov     dword ptr [rbx+10h], 0C0000095h
0x18000607a  jmp     short loc_1800060BC
0x18000607c  mov     cl, [rsp+0A8h+arg_38]
0x180006083  mov     r9, r12
0x180006086  mov     rax, [r15]
0x180006089  mov     rdx, rbx
0x18000608c  mov     [rsp+0A8h+var_70], cl
0x180006090  mov     cl, [rsp+0A8h+arg_30]
0x180006097  mov     [rsp+0A8h+var_78], cl
0x18000609b  mov     rcx, [rsp+0A8h+arg_28]
0x1800060a3  mov     rax, [rax+148h]
0x1800060aa  mov     [rsp+0A8h+var_80], rcx
0x1800060af  mov     rcx, r15
0x1800060b2  mov     [rsp+0A8h+var_88], r14d
0x1800060b7  call    _guard_dispatch_icall
0x1800060bc  mov     rcx, [rsp+0A8h+var_50]
0x1800060c1  test    rcx, rcx
0x1800060c4  jz      short loc_1800060CB
0x1800060c6  call    Kerb3961Free
0x1800060cb  mov     rax, rbx
0x1800060ce  add     rsp, 78h
0x1800060d2  pop     r15
0x1800060d4  pop     r14
0x1800060d6  pop     r12
0x1800060d8  pop     rsi
0x1800060d9  pop     rbp
0x1800060da  pop     rbx
0x1800060db  retn
```
