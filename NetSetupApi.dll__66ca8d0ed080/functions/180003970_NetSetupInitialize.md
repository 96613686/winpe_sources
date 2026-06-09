# NetSetupInitialize

- ea: `0x180003970`
- end: `0x180003b54`
- name: `NetSetupInitialize`
- size: `484`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c188`
- `0x18000c354`
- `0x18000c4a8`
- `0x18000fd78`

## callees

- `0x180003970`
- `0x180003b5c`
- `0x180005240`
- `0x18000cab4`
- `0x18000f5a0`
- `0x18000f608`
- `0x1800119f0`
- `0x180015010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800039a9`
- `RPCRT4!UuidCreate` at `0x1800039a9`

## pseudocode

```c
__int64 __fastcall NetSetupInitialize(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // edx
  __int64 v7; // rcx
  int v8; // edi
  int v9; // eax
  UUID v11; // xmm0
  UUID *p_Uuid; // r8
  _QWORD v13[4]; // [rsp+30h] [rbp-58h] BYREF
  UUID v14; // [rsp+50h] [rbp-38h]
  char v15; // [rsp+60h] [rbp-28h] BYREF
  char v16; // [rsp+61h] [rbp-27h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-20h] BYREF

  v15 = 1;
  v16 = 0;
  Uuid = 0;
  UuidCreate(&Uuid);
  if ( a1 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( v4 )
    {
      if ( *(_DWORD *)a1 == 5 )
      {
LABEL_12:
        v11 = *(UUID *)(v4 + 64);
LABEL_13:
        Uuid = v11;
      }
      else
      {
        switch ( *(_DWORD *)a1 )
        {
          case 2:
          case 3:
          case 4:
          case 9:
          case 0xC:
            goto LABEL_12;
          case 0xA:
            v11 = *(UUID *)(v4 + 4);
            goto LABEL_13;
          default:
            break;
        }
      }
    }
  }
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McTemplateU0jq_EventWriteTransfer(v5, v4, &Uuid, 1);
  v13[2] = a1;
  v13[0] = &v15;
  v13[3] = a2;
  v13[1] = &v16;
  v14 = Uuid;
  v8 = NetSetupExecuteInFrame__lambda_e7fdf54bff62e3df46c6ea5ec509f45b_(v13);
  if ( !v15 )
  {
    LODWORD(v7) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
    v8 = -2147467263;
  }
  if ( !a2 || (v7 = *a2) == 0 )
  {
    if ( (Microsoft_Windows_Network_SetupEnableBits & 1) == 0 )
      goto LABEL_8;
    p_Uuid = &Uuid;
LABEL_16:
    McTemplateU0jqd_EventWriteTransfer(v7, v6, (_DWORD)p_Uuid, 1, v8);
    goto LABEL_8;
  }
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
  {
    LODWORD(p_Uuid) = v9;
    goto LABEL_16;
  }
LABEL_8:
  if ( v8 < 0 && v16 )
    DecrementOutstandingHandles();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003970  mov     [rsp+arg_10], rbx
0x180003975  push    rdi
0x180003976  sub     rsp, 80h
0x18000397d  mov     rax, cs:__security_cookie
0x180003984  xor     rax, rsp
0x180003987  mov     [rsp+88h+var_10], rax
0x18000398c  mov     rdi, rcx
0x18000398f  mov     [rsp+88h+var_28], 1
0x180003994  xorps   xmm0, xmm0
0x180003997  mov     [rsp+88h+var_27], 0
0x18000399c  lea     rcx, [rsp+88h+Uuid]; Uuid
0x1800039a1  mov     rbx, rdx
0x1800039a4  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x1800039a9  call    cs:__imp_UuidCreate
0x1800039af  test    rdi, rdi
0x1800039b2  jnz     loc_180003A52
0x1800039b8  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1; jumptable 0000000180003AB3 default case, cases 5-8,11
0x1800039bf  jnz     loc_180003ABB
0x1800039c5  movups  xmm0, xmmword ptr [rsp+88h+Uuid.Data1]
0x1800039ca  lea     rax, [rsp+88h+var_28]
0x1800039cf  mov     [rsp+88h+var_48], rdi
0x1800039d4  mov     [rsp+88h+var_58], rax
0x1800039d9  lea     rcx, [rsp+88h+var_58]
0x1800039de  lea     rax, [rsp+88h+var_27]
0x1800039e3  mov     [rsp+88h+var_40], rbx
0x1800039e8  mov     [rsp+88h+var_50], rax
0x1800039ed  movaps  [rsp+88h+var_38], xmm0
0x1800039f2  call    NetSetupExecuteInFrame__lambda_e7fdf54bff62e3df46c6ea5ec509f45b___; NetSetupExecuteInFrame__lambda_e7fdf54bff62e3df46c6ea5ec509f45b_
0x1800039f7  cmp     [rsp+88h+var_28], 0
0x1800039fc  mov     edi, eax
0x1800039fe  jz      loc_180003AD0
0x180003a04  test    rbx, rbx
0x180003a07  jz      short loc_180003A74
0x180003a09  mov     rcx, [rbx]
0x180003a0c  test    rcx, rcx
0x180003a0f  jz      short loc_180003A74
0x180003a11  mov     rax, [rcx]
0x180003a14  mov     rax, [rax+8]
0x180003a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1d  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x180003a24  jnz     loc_180003B08
0x180003a2a  test    edi, edi
0x180003a2c  js      loc_180003B10
0x180003a32  mov     eax, edi
0x180003a34  mov     rcx, [rsp+88h+var_10]
0x180003a39  xor     rcx, rsp; StackCookie
0x180003a3c  call    __security_check_cookie
0x180003a41  mov     rbx, [rsp+88h+arg_10]
0x180003a49  add     rsp, 80h
0x180003a50  pop     rdi
0x180003a51  retn
0x180003a52  mov     rdx, [rdi+8]
0x180003a56  test    rdx, rdx
0x180003a59  jz      def_180003AB3; jumptable 0000000180003AB3 default case, cases 5-8,11
0x180003a5f  mov     eax, [rdi]
0x180003a61  cmp     eax, 5
0x180003a64  jnz     short loc_180003A93
0x180003a66  movups  xmm0, xmmword ptr [rdx+40h]; jumptable 0000000180003AB3 cases 2-4,9,12
0x180003a6a  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x180003a6f  jmp     def_180003AB3; jumptable 0000000180003AB3 default case, cases 5-8,11
0x180003a74  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x180003a7b  jz      short loc_180003A2A
0x180003a7d  lea     r8, [rsp+88h+Uuid]
0x180003a82  mov     r9d, 1
0x180003a88  mov     [rsp+88h+var_68], edi
0x180003a8c  call    McTemplateU0jqd_EventWriteTransfer
0x180003a91  jmp     short loc_180003A2A
0x180003a93  add     eax, 0FFFFFFFEh; switch 11 cases
0x180003a96  cmp     eax, 0Ah
0x180003a99  ja      def_180003AB3; jumptable 0000000180003AB3 default case, cases 5-8,11
0x180003a9f  lea     r8, cs:180000000h
0x180003aa6  cdqe
0x180003aa8  mov     ecx, ds:(jpt_180003AB3 - 180000000h)[r8+rax*4]
0x180003ab0  add     rcx, r8
0x180003ab3  jmp     rcx; switch jump
0x180003ab5  movups  xmm0, xmmword ptr [rdx+4]; jumptable 0000000180003AB3 case 10
0x180003ab9  jmp     short loc_180003A6A
0x180003abb  mov     r9d, 1
0x180003ac1  lea     r8, [rsp+88h+Uuid]
0x180003ac6  call    McTemplateU0jq_EventWriteTransfer
0x180003acb  jmp     loc_1800039C5
0x180003ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ad7  lea     rax, WPP_GLOBAL_Control
0x180003ade  cmp     rcx, rax
0x180003ae1  jz      short loc_180003AFE
0x180003ae3  cmp     byte ptr [rcx+19h], 3
0x180003ae7  jb      short loc_180003AFE
0x180003ae9  mov     rcx, [rcx+10h]
0x180003aed  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180003af4  mov     edx, 16h
0x180003af9  call    WPP_SF_
0x180003afe  mov     edi, 80004001h
0x180003b03  jmp     loc_180003A04
0x180003b08  mov     r8, rax
0x180003b0b  jmp     loc_180003A82
0x180003b10  cmp     [rsp+88h+var_27], 0
0x180003b15  jz      loc_180003A32
0x180003b1b  call    DecrementOutstandingHandles
0x180003b20  jmp     loc_180003A32
```
