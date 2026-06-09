# winreSetRecoverySequence

- ea: `0x180035e88`
- end: `0x1800361a3`
- name: `winreSetRecoverySequence`
- size: `795`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800174a0`
- `0x180018870`
- `0x180019a90`
- `0x180024a10`
- `0x18002cab4`

## callees

- `0x1800059fc`
- `0x180033864`
- `0x180035e88`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180036176`
- `ntdll!RtlNtStatusToDosError` at `0x180036176`
- `bcd!BcdSetElementData` at `0x180035f9c`
- `bcd!BcdSetElementData` at `0x180035fc9`
- `bcd!BcdSetElementData` at `0x180036021`
- `bcd!BcdSetElementData` at `0x18003603d`
- `bcd!BcdSetElementData` at `0x1800360b8`
- `bcd!BcdSetElementData` at `0x1800360f2`
- `bcd!BcdSetElementData` at `0x180035f9c`
- `bcd!BcdSetElementData` at `0x180035fc9`
- `bcd!BcdSetElementData` at `0x180036021`
- `bcd!BcdSetElementData` at `0x18003603d`
- `bcd!BcdSetElementData` at `0x1800360b8`
- `bcd!BcdSetElementData` at `0x1800360f2`
- `bcd!BcdCloseStore` at `0x180036146`
- `bcd!BcdCloseStore` at `0x180036146`
- `bcd!BcdCloseObject` at `0x180036054`
- `bcd!BcdCloseObject` at `0x180036067`
- `bcd!BcdCloseObject` at `0x180036118`
- `bcd!BcdCloseObject` at `0x18003612f`
- `bcd!BcdCloseObject` at `0x180036054`
- `bcd!BcdCloseObject` at `0x180036067`
- `bcd!BcdCloseObject` at `0x180036118`
- `bcd!BcdCloseObject` at `0x18003612f`
- `bcd!BcdGetElementData` at `0x180035ff2`
- `bcd!BcdGetElementData` at `0x180035ff2`
- `bcd!BcdOpenObject` at `0x180035f2f`
- `bcd!BcdOpenObject` at `0x180036008`
- `bcd!BcdOpenObject` at `0x180036089`
- `bcd!BcdOpenObject` at `0x180035f2f`
- `bcd!BcdOpenObject` at `0x180036008`
- `bcd!BcdOpenObject` at `0x180036089`
- `bcd!BcdOpenStore` at `0x180035ef9`
- `bcd!BcdOpenStore` at `0x180035ef9`

## string_xrefs

- `0x180035f57`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180035f05`: `winreSetRecoverySequence open store failed: %x`
- `0x180035f3b`: `winreSetRecoverySequenceBcdOpenObject filed: 0x%x`
- `0x180036095`: `winreSetRecoverySequenceBcdOpenObject failed: 0x%x`

## pseudocode

```c
ULONG __fastcall winreSetRecoverySequence(__int128 *a1, int a2, struct _GUID *a3)
{
  int v6; // eax
  NTSTATUS IdForCurrentOS; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-39h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h] BYREF
  void *v17; // [rsp+40h] [rbp-29h] BYREF
  _WORD v18[2]; // [rsp+48h] [rbp-21h] BYREF
  int v19; // [rsp+4Ch] [rbp-1Dh] BYREF
  __int128 v20; // [rsp+50h] [rbp-19h] BYREF
  struct _GUID v21; // [rsp+60h] [rbp-9h] BYREF
  __int128 v22; // [rsp+70h] [rbp+7h] BYREF
  __int128 v23; // [rsp+80h] [rbp+17h] BYREF

  v15 = 0;
  v18[0] = 1;
  v17 = 0;
  v16 = 0;
  v19 = 16;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v6 = BcdOpenStore(0, 0, &v17);
  IdForCurrentOS = v6;
  if ( v6 < 0 )
  {
    UnattendLogW(2, L"winreSetRecoverySequence open store failed: %x", (unsigned int)v6);
    goto LABEL_28;
  }
  if ( a3 )
  {
    v21 = *a3;
  }
  else
  {
    IdForCurrentOS = winreGetIdForCurrentOS(v17, &v21);
    if ( IdForCurrentOS < 0 )
    {
      UnattendLogW(
        2,
        L"winreSetRecoverySequence %s (0x%x) in file %S line %d",
        L"failed to get id for current os",
        (unsigned int)IdForCurrentOS,
        "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
        680);
      goto LABEL_28;
    }
  }
  v8 = BcdOpenObject(v17, &v21, &v15);
  IdForCurrentOS = v8;
  if ( v8 < 0 )
  {
    UnattendLogW(2, L"winreSetRecoverySequenceBcdOpenObject filed: 0x%x", (unsigned int)v8);
    goto LABEL_28;
  }
  v9 = BcdSetElementData(v15, 335544328, a1, 16);
  IdForCurrentOS = v9;
  if ( v9 < 0 )
    goto LABEL_10;
  v10 = BcdSetElementData(v15, 369098761, v18, 2);
  IdForCurrentOS = v10;
  if ( v10 < 0 )
    goto LABEL_12;
  if ( (int)BcdGetElementData(v15, 587202563, &v22, &v19) < 0 || (int)BcdOpenObject(v17, &v22, &v16) < 0 )
    goto LABEL_17;
  v9 = BcdSetElementData(v16, 335544328, a1, 16);
  IdForCurrentOS = v9;
  if ( v9 < 0 )
  {
LABEL_10:
    UnattendLogW(2, L"winreSetRecoverySequenceBcdSetElementData(recoverysequence) failed: 0x%x", (unsigned int)v9);
    goto LABEL_28;
  }
  v10 = BcdSetElementData(v16, 369098761, v18, 2);
  IdForCurrentOS = v10;
  if ( v10 < 0 )
  {
LABEL_12:
    UnattendLogW(2, L"winreSetRecoverySequenceBcdSetElementData(recoveryenabled) failed: 0x%x", (unsigned int)v10);
  }
  else
  {
LABEL_17:
    IdForCurrentOS = 0;
    if ( v16 )
    {
      BcdCloseObject();
      v16 = 0;
    }
    if ( v15 )
    {
      BcdCloseObject();
      v15 = 0;
    }
    if ( a2 )
    {
      v11 = BcdOpenObject(v17, &GUID_WINDOWS_BOOTMGR, &v15);
      IdForCurrentOS = v11;
      if ( v11 >= 0 )
      {
        v23 = *a1;
        v12 = BcdSetElementData(v15, 1409286159, &v23, 16);
        IdForCurrentOS = v12;
        if ( v12 >= 0 )
        {
          WORD1(v20) = a2;
          LOWORD(v20) = 1;
          WORD3(v20) = 1;
          DWORD2(v20) = 1409286159;
          v13 = BcdSetElementData(v15, 654311472, &v20, 16);
          IdForCurrentOS = v13;
          if ( v13 < 0 )
            UnattendLogW(
              2,
              L"winreSetRecoverySequenceBcdSetElementData BCDE_BOOTMGR_TYPE_CUSTOM_ACTIONS_LIST failed: 0x%x",
              (unsigned int)v13);
        }
        else
        {
          UnattendLogW(
            2,
            L"winreSetRecoverySequenceBcdSetElementData BCDE_CUSTOM_ACTION_APPLICATION_LIST failed: 0x%x",
            (unsigned int)v12);
        }
      }
      else
      {
        UnattendLogW(2, L"winreSetRecoverySequenceBcdOpenObject failed: 0x%x", (unsigned int)v11);
      }
    }
  }
LABEL_28:
  if ( v16 )
  {
    BcdCloseObject();
    v16 = 0;
  }
  if ( v15 )
  {
    BcdCloseObject();
    v15 = 0;
  }
  if ( v17 )
    BcdCloseStore();
  if ( IdForCurrentOS >= 0 )
    return 0;
  if ( !ReAgentError )
    ReAgentError = 7;
  UnattendLogW(2, L"winreSetRecoverySequencewinreSetRecoverySequence failed: 0x%x", (unsigned int)IdForCurrentOS);
  return RtlNtStatusToDosError(IdForCurrentOS);
}

```

## disassembly

```asm
0x180035e88  mov     [rsp-8+arg_18], rbx
0x180035e8d  push    rbp
0x180035e8e  push    rsi
0x180035e8f  push    rdi
0x180035e90  push    r12
0x180035e92  push    r14
0x180035e94  lea     rbp, [rsp-37h]
0x180035e99  sub     rsp, 0A0h
0x180035ea0  mov     rax, cs:__security_cookie
0x180035ea7  xor     rax, rsp
0x180035eaa  mov     [rbp+57h+var_30], rax
0x180035eae  xorps   xmm0, xmm0
0x180035eb1  mov     [rbp+57h+var_90], 0
0x180035eb9  mov     rdi, r8
0x180035ebc  mov     [rbp+57h+var_78], 1
0x180035ec2  mov     r14d, edx
0x180035ec5  mov     [rbp+57h+var_80], 0
0x180035ecd  mov     rsi, rcx
0x180035ed0  mov     [rbp+57h+var_88], 0
0x180035ed8  xorps   xmm1, xmm1
0x180035edb  lea     r8, [rbp+57h+var_80]
0x180035edf  mov     r12d, 10h
0x180035ee5  xor     edx, edx
0x180035ee7  xor     ecx, ecx
0x180035ee9  mov     [rbp+57h+var_74], r12d
0x180035eed  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180035ef1  movups  [rbp+57h+var_70], xmm0
0x180035ef5  movups  [rbp+57h+var_50], xmm1
0x180035ef9  call    cs:__imp_BcdOpenStore
0x180035eff  mov     ebx, eax
0x180035f01  test    eax, eax
0x180035f03  jns     short loc_180035F16
0x180035f05  lea     rdx, aWinresetrecove_5; "winreSetRecoverySequence open store fai"...
0x180035f0c  mov     edi, 2
0x180035f11  jmp     loc_180036105
0x180035f16  test    rdi, rdi
0x180035f19  jz      short loc_180035F44
0x180035f1b  movups  xmm0, xmmword ptr [rdi]
0x180035f1e  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180035f23  mov     rcx, [rbp+57h+var_80]
0x180035f27  lea     r8, [rbp+57h+var_90]
0x180035f2b  lea     rdx, [rbp+57h+var_60]
0x180035f2f  call    cs:__imp_BcdOpenObject
0x180035f35  mov     ebx, eax
0x180035f37  test    eax, eax
0x180035f39  jns     short loc_180035F8D
0x180035f3b  lea     rdx, aWinresetrecove_12; "winreSetRecoverySequenceBcdOpenObject f"...
0x180035f42  jmp     short loc_180035F0C
0x180035f44  mov     rcx, [rbp+57h+var_80]; void *
0x180035f48  lea     rdx, [rbp+57h+var_60]; struct _GUID *
0x180035f4c  call    ?winreGetIdForCurrentOS@@YAJPEAXPEAU_GUID@@@Z; winreGetIdForCurrentOS(void *,_GUID *)
0x180035f51  mov     ebx, eax
0x180035f53  test    eax, eax
0x180035f55  jns     short loc_180035F23
0x180035f57  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180035f5e  mov     [rsp+0C0h+var_98], 2A8h
0x180035f66  mov     edi, 2
0x180035f6b  mov     [rsp+0C0h+var_A0], rax
0x180035f70  mov     ecx, edi
0x180035f72  lea     r8, aFailedToGetIdF; "failed to get id for current os"
0x180035f79  mov     r9d, ebx
0x180035f7c  lea     rdx, aWinresetrecove_19; "winreSetRecoverySequence %s (0x%x) in f"...
0x180035f83  call    UnattendLogW
0x180035f88  jmp     loc_18003610F
0x180035f8d  mov     rcx, [rbp+57h+var_90]
0x180035f91  mov     r9d, r12d
0x180035f94  mov     r8, rsi
0x180035f97  mov     edx, 14000008h
0x180035f9c  call    cs:__imp_BcdSetElementData
0x180035fa2  mov     ebx, eax
0x180035fa4  mov     edi, 2
0x180035fa9  test    eax, eax
0x180035fab  jns     short loc_180035FB9
0x180035fad  lea     rdx, aWinresetrecove_3; "winreSetRecoverySequenceBcdSetElementDa"...
0x180035fb4  jmp     loc_180036105
0x180035fb9  mov     rcx, [rbp+57h+var_90]
0x180035fbd  lea     r8, [rbp+57h+var_78]
0x180035fc1  mov     r9d, edi
0x180035fc4  mov     edx, 16000009h
0x180035fc9  call    cs:__imp_BcdSetElementData
0x180035fcf  mov     ebx, eax
0x180035fd1  test    eax, eax
0x180035fd3  jns     short loc_180035FE1
0x180035fd5  lea     rdx, aWinresetrecove_10; "winreSetRecoverySequenceBcdSetElementDa"...
0x180035fdc  jmp     loc_180036105
0x180035fe1  mov     rcx, [rbp+57h+var_90]
0x180035fe5  lea     r9, [rbp+57h+var_74]
0x180035fe9  lea     r8, [rbp+57h+var_50]
0x180035fed  mov     edx, 23000003h
0x180035ff2  call    cs:__imp_BcdGetElementData
0x180035ff8  test    eax, eax
0x180035ffa  js      short loc_180036049
0x180035ffc  mov     rcx, [rbp+57h+var_80]
0x180036000  lea     r8, [rbp+57h+var_88]
0x180036004  lea     rdx, [rbp+57h+var_50]
0x180036008  call    cs:__imp_BcdOpenObject
0x18003600e  test    eax, eax
0x180036010  js      short loc_180036049
0x180036012  mov     rcx, [rbp+57h+var_88]
0x180036016  mov     r9d, r12d
0x180036019  mov     r8, rsi
0x18003601c  mov     edx, 14000008h
0x180036021  call    cs:__imp_BcdSetElementData
0x180036027  mov     ebx, eax
0x180036029  test    eax, eax
0x18003602b  js      short loc_180035FAD
0x18003602d  mov     rcx, [rbp+57h+var_88]
0x180036031  lea     r8, [rbp+57h+var_78]
0x180036035  mov     r9d, edi
0x180036038  mov     edx, 16000009h
0x18003603d  call    cs:__imp_BcdSetElementData
0x180036043  mov     ebx, eax
0x180036045  test    eax, eax
0x180036047  js      short loc_180035FD5
0x180036049  mov     rcx, [rbp+57h+var_88]
0x18003604d  xor     ebx, ebx
0x18003604f  test    rcx, rcx
0x180036052  jz      short loc_18003605E
0x180036054  call    cs:__imp_BcdCloseObject
0x18003605a  mov     [rbp+57h+var_88], rbx
0x18003605e  mov     rcx, [rbp+57h+var_90]
0x180036062  test    rcx, rcx
0x180036065  jz      short loc_180036071
0x180036067  call    cs:__imp_BcdCloseObject
0x18003606d  mov     [rbp+57h+var_90], rbx
0x180036071  test    r14d, r14d
0x180036074  jz      loc_18003610F
0x18003607a  mov     rcx, [rbp+57h+var_80]
0x18003607e  lea     r8, [rbp+57h+var_90]
0x180036082  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180036089  call    cs:__imp_BcdOpenObject
0x18003608f  mov     ebx, eax
0x180036091  test    eax, eax
0x180036093  jns     short loc_18003609E
0x180036095  lea     rdx, aWinresetrecove_17; "winreSetRecoverySequenceBcdOpenObject f"...
0x18003609c  jmp     short loc_180036105
0x18003609e  movups  xmm0, xmmword ptr [rsi]
0x1800360a1  mov     rcx, [rbp+57h+var_90]
0x1800360a5  lea     r8, [rbp+57h+var_40]
0x1800360a9  mov     esi, 5400000Fh
0x1800360ae  mov     r9d, r12d
0x1800360b1  mov     edx, esi
0x1800360b3  movdqu  [rbp+57h+var_40], xmm0
0x1800360b8  call    cs:__imp_BcdSetElementData
0x1800360be  mov     ebx, eax
0x1800360c0  test    eax, eax
0x1800360c2  jns     short loc_1800360CD
0x1800360c4  lea     rdx, aWinresetrecove_2; "winreSetRecoverySequenceBcdSetElementDa"...
0x1800360cb  jmp     short loc_180036105
0x1800360cd  mov     rcx, [rbp+57h+var_90]
0x1800360d1  lea     r8, [rbp+57h+var_70]
0x1800360d5  mov     eax, 1
0x1800360da  mov     word ptr [rbp+57h+var_70+2], r14w
0x1800360df  mov     r9d, r12d
0x1800360e2  mov     word ptr [rbp+57h+var_70], ax
0x1800360e6  mov     edx, 27000030h
0x1800360eb  mov     word ptr [rbp+57h+var_70+6], ax
0x1800360ef  mov     dword ptr [rbp+57h+var_70+8], esi
0x1800360f2  call    cs:__imp_BcdSetElementData
0x1800360f8  mov     ebx, eax
0x1800360fa  test    eax, eax
0x1800360fc  jns     short loc_18003610F
0x1800360fe  lea     rdx, aWinresetrecove_14; "winreSetRecoverySequenceBcdSetElementDa"...
0x180036105  mov     r8d, eax
0x180036108  mov     ecx, edi
0x18003610a  call    UnattendLogW
0x18003610f  mov     rcx, [rbp+57h+var_88]
0x180036113  test    rcx, rcx
0x180036116  jz      short loc_180036126
0x180036118  call    cs:__imp_BcdCloseObject
0x18003611e  mov     [rbp+57h+var_88], 0
0x180036126  mov     rcx, [rbp+57h+var_90]
0x18003612a  test    rcx, rcx
0x18003612d  jz      short loc_18003613D
0x18003612f  call    cs:__imp_BcdCloseObject
0x180036135  mov     [rbp+57h+var_90], 0
0x18003613d  mov     rcx, [rbp+57h+var_80]
0x180036141  test    rcx, rcx
0x180036144  jz      short loc_18003614C
0x180036146  call    cs:__imp_BcdCloseStore
0x18003614c  test    ebx, ebx
0x18003614e  jns     short loc_18003617E
0x180036150  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180036157  jnz     short loc_180036163
0x180036159  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180036163  mov     r8d, ebx
0x180036166  lea     rdx, aWinresetrecove_11; "winreSetRecoverySequencewinreSetRecover"...
0x18003616d  mov     ecx, edi
0x18003616f  call    UnattendLogW
0x180036174  mov     ecx, ebx; Status
0x180036176  call    cs:__imp_RtlNtStatusToDosError
0x18003617c  jmp     short loc_180036180
0x18003617e  xor     eax, eax
0x180036180  mov     rcx, [rbp+57h+var_30]
0x180036184  xor     rcx, rsp; StackCookie
0x180036187  call    __security_check_cookie
0x18003618c  mov     rbx, [rsp+0C0h+arg_18]
0x180036194  add     rsp, 0A0h
0x18003619b  pop     r14
0x18003619d  pop     r12
0x18003619f  pop     rdi
0x1800361a0  pop     rsi
0x1800361a1  pop     rbp
0x1800361a2  retn
```
