# Kerb3961::SSPICipherSuite<1,1,1>::GSSGetMIC(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180004ec0`
- end: `0x180004f72`
- name: `?GSSGetMIC@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `178`
- prototype: `__int64 __fastcall(int, int, int, int, char *, __int64, char, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004ec0`
- `0x180011760`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::GSSGetMIC(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char *a5)
{
  if ( (_DWORD)a5 == -2147483647 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"QOP != KERB_WRAP_NO_ENCRYPT",
      (const char *)0x80000001LL);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893046;
  }
  else if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 328LL))(a1, a2);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"inputMessage.length <= MessageLimit",
      (const char *)(unsigned int)a5);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
  }
  return a2;
}

```

## disassembly

```asm
0x180004ec0  push    rbx
0x180004ec2  sub     rsp, 50h
0x180004ec6  mov     rbx, rdx
0x180004ec9  mov     r10, rcx
0x180004ecc  mov     edx, dword ptr [rsp+58h+arg_20]; char *
0x180004ed3  cmp     edx, 80000001h
0x180004ed9  jnz     short loc_180004EFF
0x180004edb  lea     rcx, aQopKerbWrapNoE; "QOP != KERB_WRAP_NO_ENCRYPT"
0x180004ee2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004ee7  mov     qword ptr [rbx], 0
0x180004eee  mov     qword ptr [rbx+8], 0
0x180004ef6  mov     dword ptr [rbx+10h], 8009030Ah
0x180004efd  jmp     short loc_180004F68
0x180004eff  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180004f06  jbe     short loc_180004F2C
0x180004f08  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180004f0f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004f14  mov     qword ptr [rbx], 0
0x180004f1b  mov     qword ptr [rbx+8], 0
0x180004f23  mov     dword ptr [rbx+10h], 0C0000095h
0x180004f2a  jmp     short loc_180004F68
0x180004f2c  mov     rax, [rcx]
0x180004f2f  mov     cl, [rsp+58h+arg_38]
0x180004f36  mov     [rsp+58h+var_20], cl
0x180004f3a  mov     cl, [rsp+58h+arg_30]
0x180004f41  mov     rax, [rax+148h]
0x180004f48  mov     [rsp+58h+var_28], cl
0x180004f4c  mov     rcx, [rsp+58h+arg_28]
0x180004f54  mov     [rsp+58h+var_30], rcx
0x180004f59  mov     rcx, r10
0x180004f5c  mov     [rsp+58h+var_38], edx
0x180004f60  mov     rdx, rbx
0x180004f63  call    _guard_dispatch_icall
0x180004f68  mov     rax, rbx
0x180004f6b  add     rsp, 50h
0x180004f6f  pop     rbx
0x180004f70  retn
```
