# winreSetBCDDisplayMessage

- ea: `0x180035c90`
- end: `0x180035e82`
- name: `winreSetBCDDisplayMessage`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180026670`

## callees

- `0x1800059fc`
- `0x18000ed74`
- `0x180033864`
- `0x180035c90`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035e61`
- `ntdll!RtlNtStatusToDosError` at `0x180035e61`
- `bcd!BcdSetElementData` at `0x180035df1`
- `bcd!BcdSetElementData` at `0x180035df1`
- `bcd!BcdCloseStore` at `0x180035e2e`
- `bcd!BcdCloseStore` at `0x180035e2e`
- `bcd!BcdCloseObject` at `0x180035e17`
- `bcd!BcdCloseObject` at `0x180035e17`
- `bcd!BcdOpenObject` at `0x180035dc9`
- `bcd!BcdOpenObject` at `0x180035dc9`
- `bcd!BcdOpenStore` at `0x180035d54`
- `bcd!BcdOpenStore` at `0x180035d54`

## string_xrefs

- `0x180035dd5`: `BcdOpenObject failed: 0x%x`
- `0x180035d8c`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180035d60`: `Open store failed: 0x%x`

## pseudocode

```c
ULONG __fastcall winreSetBCDDisplayMessage(__int64 a1, int a2)
{
  __int64 v2; // rax
  NTSTATUS IdForCurrentOS; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp-30h] BYREF
  void *v9; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  struct _GUID v11; // [rsp+48h] [rbp-18h] BYREF

  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)(a2 - 1) > 0x15 )
  {
    IdForCurrentOS = -1073741811;
    goto LABEL_27;
  }
  switch ( a2 )
  {
    case 1:
      v10 = 5;
      break;
    case 2:
      v10 = 7;
      break;
    case 7:
    case 8:
      goto LABEL_12;
    case 9:
      v10 = 4;
      break;
    case 10:
      v10 = 6;
      break;
    default:
      if ( (unsigned int)(a2 - 17) >= 2 )
      {
        v2 = 3;
LABEL_13:
        v10 = v2;
        if ( a2 == 5 )
        {
          IdForCurrentOS = 0;
          if ( (unsigned int)winreIsWinPE() )
            goto LABEL_27;
        }
        break;
      }
LABEL_12:
      v2 = 8;
      goto LABEL_13;
  }
  v4 = BcdOpenStore(0, 0, &v9);
  IdForCurrentOS = v4;
  if ( v4 >= 0 )
  {
    IdForCurrentOS = winreGetIdForCurrentOS(v9, &v11);
    if ( IdForCurrentOS >= 0 )
    {
      v5 = BcdOpenObject(v9, &v11, &v8);
      IdForCurrentOS = v5;
      if ( v5 >= 0 )
      {
        v6 = BcdSetElementData(v8, 352321638, &v10, 8);
        IdForCurrentOS = v6;
        if ( v6 < 0 )
          UnattendLogW(1, L"BcdSetElementData failed: 0x%x", (unsigned int)v6);
      }
      else
      {
        UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v5);
      }
    }
    else
    {
      UnattendLogW(
        2,
        L"winreSetBCDDisplayMessage %s (0x%x) in file %S line %d",
        L"failed to get id for current os",
        (unsigned int)IdForCurrentOS,
        "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
        590);
    }
  }
  else
  {
    UnattendLogW(1, L"Open store failed: 0x%x", (unsigned int)v4);
  }
LABEL_27:
  if ( v8 )
  {
    BcdCloseObject();
    v8 = 0;
  }
  if ( v9 )
    BcdCloseStore(v9);
  if ( IdForCurrentOS >= 0 )
    return 0;
  if ( !ReAgentError )
    ReAgentError = 7;
  UnattendLogW(1, L"winreSetBCDDisplayMessage failed: 0x%x", (unsigned int)IdForCurrentOS);
  return RtlNtStatusToDosError(IdForCurrentOS);
}

```

## disassembly

```asm
0x180035c90  mov     [rsp-8+arg_0], rbx
0x180035c95  push    rbp
0x180035c96  mov     rbp, rsp
0x180035c99  sub     rsp, 60h
0x180035c9d  mov     rax, cs:__security_cookie
0x180035ca4  xor     rax, rsp
0x180035ca7  mov     [rbp+var_8], rax
0x180035cab  lea     eax, [rdx-1]
0x180035cae  mov     [rbp+var_28], 0
0x180035cb6  mov     [rbp+var_30], 0
0x180035cbe  xorps   xmm0, xmm0
0x180035cc1  mov     [rbp+var_20], 0
0x180035cc9  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x180035ccd  cmp     eax, 15h
0x180035cd0  ja      loc_180035E09
0x180035cd6  mov     ecx, edx
0x180035cd8  sub     ecx, 1
0x180035cdb  jz      short loc_180035D44
0x180035cdd  sub     ecx, 1
0x180035ce0  jz      short loc_180035D3A
0x180035ce2  sub     ecx, 5
0x180035ce5  jz      short loc_180035D1B
0x180035ce7  sub     ecx, 1
0x180035cea  jz      short loc_180035D1B
0x180035cec  sub     ecx, 1
0x180035cef  jz      short loc_180035D11
0x180035cf1  sub     ecx, 1
0x180035cf4  jz      short loc_180035D07
0x180035cf6  sub     ecx, 7
0x180035cf9  jz      short loc_180035D1B
0x180035cfb  cmp     ecx, 1
0x180035cfe  jz      short loc_180035D1B
0x180035d00  mov     eax, 3
0x180035d05  jmp     short loc_180035D20
0x180035d07  mov     [rbp+var_20], 6
0x180035d0f  jmp     short loc_180035D4C
0x180035d11  mov     [rbp+var_20], 4
0x180035d19  jmp     short loc_180035D4C
0x180035d1b  mov     eax, 8
0x180035d20  mov     [rbp+var_20], rax
0x180035d24  cmp     edx, 5
0x180035d27  jnz     short loc_180035D4C
0x180035d29  xor     ebx, ebx
0x180035d2b  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x180035d30  test    eax, eax
0x180035d32  jnz     loc_180035E0E
0x180035d38  jmp     short loc_180035D4C
0x180035d3a  mov     [rbp+var_20], 7
0x180035d42  jmp     short loc_180035D4C
0x180035d44  mov     [rbp+var_20], 5
0x180035d4c  lea     r8, [rbp+var_28]
0x180035d50  xor     edx, edx
0x180035d52  xor     ecx, ecx
0x180035d54  call    cs:__imp_BcdOpenStore
0x180035d5a  mov     ebx, eax
0x180035d5c  test    eax, eax
0x180035d5e  jns     short loc_180035D79
0x180035d60  lea     rdx, aOpenStoreFaile; "Open store failed: 0x%x"
0x180035d67  mov     r8d, eax
0x180035d6a  mov     ecx, 1
0x180035d6f  call    UnattendLogW
0x180035d74  jmp     loc_180035E0E
0x180035d79  mov     rcx, [rbp+var_28]; void *
0x180035d7d  lea     rdx, [rbp+var_18]; struct _GUID *
0x180035d81  call    ?winreGetIdForCurrentOS@@YAJPEAXPEAU_GUID@@@Z; winreGetIdForCurrentOS(void *,_GUID *)
0x180035d86  mov     ebx, eax
0x180035d88  test    eax, eax
0x180035d8a  jns     short loc_180035DBD
0x180035d8c  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180035d93  mov     [rsp+60h+var_38], 24Eh
0x180035d9b  mov     r9d, ebx
0x180035d9e  mov     [rsp+60h+var_40], rax
0x180035da3  lea     r8, aFailedToGetIdF; "failed to get id for current os"
0x180035daa  mov     ecx, 2
0x180035daf  lea     rdx, aWinresetbcddis; "winreSetBCDDisplayMessage %s (0x%x) in "...
0x180035db6  call    UnattendLogW
0x180035dbb  jmp     short loc_180035E0E
0x180035dbd  mov     rcx, [rbp+var_28]
0x180035dc1  lea     r8, [rbp+var_30]
0x180035dc5  lea     rdx, [rbp+var_18]
0x180035dc9  call    cs:__imp_BcdOpenObject
0x180035dcf  mov     ebx, eax
0x180035dd1  test    eax, eax
0x180035dd3  jns     short loc_180035DDE
0x180035dd5  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x180035ddc  jmp     short loc_180035D67
0x180035dde  mov     rcx, [rbp+var_30]
0x180035de2  lea     r8, [rbp+var_20]
0x180035de6  mov     r9d, 8
0x180035dec  mov     edx, 15000066h
0x180035df1  call    cs:__imp_BcdSetElementData
0x180035df7  mov     ebx, eax
0x180035df9  test    eax, eax
0x180035dfb  jns     short loc_180035E0E
0x180035dfd  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180035e04  jmp     loc_180035D67
0x180035e09  mov     ebx, 0C000000Dh
0x180035e0e  mov     rcx, [rbp+var_30]
0x180035e12  test    rcx, rcx
0x180035e15  jz      short loc_180035E25
0x180035e17  call    cs:__imp_BcdCloseObject
0x180035e1d  mov     [rbp+var_30], 0
0x180035e25  mov     rcx, [rbp+var_28]
0x180035e29  test    rcx, rcx
0x180035e2c  jz      short loc_180035E34
0x180035e2e  call    cs:__imp_BcdCloseStore
0x180035e34  test    ebx, ebx
0x180035e36  jns     short loc_180035E69
0x180035e38  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180035e3f  jnz     short loc_180035E4B
0x180035e41  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180035e4b  mov     r8d, ebx
0x180035e4e  lea     rdx, aWinresetbcddis_0; "winreSetBCDDisplayMessage failed: 0x%x"
0x180035e55  mov     ecx, 1
0x180035e5a  call    UnattendLogW
0x180035e5f  mov     ecx, ebx; Status
0x180035e61  call    cs:__imp_RtlNtStatusToDosError
0x180035e67  jmp     short loc_180035E6B
0x180035e69  xor     eax, eax
0x180035e6b  mov     rcx, [rbp+var_8]
0x180035e6f  xor     rcx, rsp; StackCookie
0x180035e72  call    __security_check_cookie
0x180035e77  mov     rbx, [rsp+60h+arg_0]
0x180035e7c  add     rsp, 60h
0x180035e80  pop     rbp
0x180035e81  retn
```
