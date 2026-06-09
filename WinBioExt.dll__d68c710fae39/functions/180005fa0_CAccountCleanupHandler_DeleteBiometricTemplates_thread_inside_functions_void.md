# CAccountCleanupHandler::DeleteBiometricTemplates(thread_inside_functions &,void *)

- ea: `0x180005fa0`
- end: `0x180006112`
- name: `?DeleteBiometricTemplates@CAccountCleanupHandler@@CAJAEAVthread_inside_functions@@PEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct thread_inside_functions *, char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005fa0`

## import_xrefs

- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioCloseSession` at `0x1800060e3`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioCloseSession` at `0x1800060e3`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioFree` at `0x1800060ed`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioFree` at `0x1800060ed`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioDeleteTemplate` at `0x1800060ce`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioDeleteTemplate` at `0x1800060ce`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioEnumBiometricUnits` at `0x180006022`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioEnumBiometricUnits` at `0x180006022`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioOpenSession` at `0x180006098`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioOpenSession` at `0x180006098`

## pseudocode

```c
__int64 __fastcall CAccountCleanupHandler::DeleteBiometricTemplates(struct thread_inside_functions *a1, char *a2)
{
  HRESULT v5; // esi
  WINBIO_BIOMETRIC_TYPE i; // edi
  int v7; // ecx
  WINBIO_UNIT_SCHEMA *v8; // rcx
  __int64 v9; // rdx
  SIZE_T v10; // rax
  SIZE_T j; // rbx
  WINBIO_SESSION_HANDLE SessionHandle; // [rsp+88h] [rbp+48h] BYREF
  WINBIO_UNIT_SCHEMA *UnitSchemaArray; // [rsp+90h] [rbp+50h] BYREF
  SIZE_T UnitCount; // [rsp+98h] [rbp+58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = 0;
  ++dword_1800105B4;
  for ( i = 1; _InterlockedCompareExchange((volatile signed __int32 *)a1 + 26, 2, 2) == 2; i *= 2 )
  {
    v7 = *((_DWORD *)a2 + 3);
    if ( !v7 )
      break;
    if ( (v7 & i) != 0 )
    {
      UnitSchemaArray = 0;
      UnitCount = 0;
      *((_DWORD *)a2 + 3) = v7 & ~i;
      v5 = WinBioEnumBiometricUnits(i, &UnitSchemaArray, &UnitCount);
      if ( v5 >= 0 )
      {
        v8 = UnitSchemaArray;
        if ( UnitSchemaArray )
        {
          if ( UnitCount )
          {
            v9 = 0;
            while ( UnitSchemaArray[v9].PoolType != 1 )
            {
              if ( ++v9 >= UnitCount )
                goto LABEL_21;
            }
            SessionHandle = 0;
            v5 = WinBioOpenSession(i, 1u, 0, 0, 0, (GUID *)1, &SessionHandle);
            if ( v5 >= 0 )
            {
              v10 = UnitCount;
              for ( j = 0; j < v10; ++j )
              {
                if ( UnitSchemaArray[j].PoolType == 1 )
                {
                  WinBioDeleteTemplate(SessionHandle, UnitSchemaArray[j].UnitId, (WINBIO_IDENTITY *)(a2 + 16), 0xFFu);
                  v10 = UnitCount;
                }
              }
              WinBioCloseSession(SessionHandle);
            }
            v8 = UnitSchemaArray;
LABEL_21:
            WinBioFree(v8);
          }
        }
      }
    }
  }
  --dword_1800105B4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005fa0  push    rbp
0x180005fa2  push    rbx
0x180005fa3  push    rsi
0x180005fa4  push    rdi
0x180005fa5  push    r13
0x180005fa7  push    r14
0x180005fa9  push    r15
0x180005fab  mov     rbp, rsp
0x180005fae  sub     rsp, 40h
0x180005fb2  mov     r14, rdx
0x180005fb5  mov     r15, rcx
0x180005fb8  test    rdx, rdx
0x180005fbb  jnz     short loc_180005FC7
0x180005fbd  mov     eax, 80004003h
0x180005fc2  jmp     loc_180006103
0x180005fc7  xor     esi, esi
0x180005fc9  lea     r13d, [rsi+1]
0x180005fcd  add     cs:dword_1800105B4, r13d
0x180005fd4  mov     edi, r13d
0x180005fd7  mov     ecx, 2
0x180005fdc  mov     eax, ecx
0x180005fde  lock cmpxchg [r15+68h], ecx
0x180005fe4  jnz     loc_1800060FA
0x180005fea  mov     ecx, [r14+0Ch]
0x180005fee  test    ecx, ecx
0x180005ff0  jz      loc_1800060FA
0x180005ff6  test    edi, ecx
0x180005ff8  jz      loc_1800060F3
0x180005ffe  mov     eax, edi
0x180006000  mov     [rbp+UnitSchemaArray], 0
0x180006008  not     eax
0x18000600a  mov     [rbp+UnitCount], 0
0x180006012  and     eax, ecx
0x180006014  lea     r8, [rbp+UnitCount]; UnitCount
0x180006018  mov     ecx, edi; Factor
0x18000601a  mov     [r14+0Ch], eax
0x18000601e  lea     rdx, [rbp+UnitSchemaArray]; UnitSchemaArray
0x180006022  call    cs:__imp_WinBioEnumBiometricUnits
0x180006028  mov     esi, eax
0x18000602a  test    eax, eax
0x18000602c  js      loc_1800060F3
0x180006032  mov     rcx, [rbp+UnitSchemaArray]
0x180006036  test    rcx, rcx
0x180006039  jz      loc_1800060F3
0x18000603f  mov     r8, [rbp+UnitCount]
0x180006043  test    r8, r8
0x180006046  jz      loc_1800060F3
0x18000604c  xor     edx, edx
0x18000604e  test    r8, r8
0x180006051  jz      loc_1800060ED
0x180006057  imul    rax, rdx, 0A1Ch
0x18000605e  cmp     [rax+rcx+4], r13d
0x180006063  jz      short loc_18000606F
0x180006065  add     rdx, r13
0x180006068  cmp     rdx, r8
0x18000606b  jb      short loc_180006057
0x18000606d  jmp     short loc_1800060ED
0x18000606f  lea     rax, [rbp+arg_8]
0x180006073  mov     [rbp+arg_8], 0
0x18000607a  mov     [rsp+40h+SessionHandle], rax; SessionHandle
0x18000607f  xor     r9d, r9d; UnitArray
0x180006082  mov     [rsp+40h+DatabaseId], r13; DatabaseId
0x180006087  xor     r8d, r8d; Flags
0x18000608a  mov     edx, r13d; PoolType
0x18000608d  mov     [rsp+40h+var_20], 0; UnitCount
0x180006096  mov     ecx, edi; Factor
0x180006098  call    cs:__imp_WinBioOpenSession
0x18000609e  mov     esi, eax
0x1800060a0  test    eax, eax
0x1800060a2  js      short loc_1800060E9
0x1800060a4  mov     rax, [rbp+UnitCount]
0x1800060a8  xor     ebx, ebx
0x1800060aa  test    rax, rax
0x1800060ad  jz      short loc_1800060E0
0x1800060af  mov     rcx, [rbp+UnitSchemaArray]
0x1800060b3  imul    rdx, rbx, 0A1Ch
0x1800060ba  cmp     [rdx+rcx+4], r13d
0x1800060bf  jnz     short loc_1800060D8
0x1800060c1  mov     edx, [rdx+rcx]; UnitId
0x1800060c4  lea     r8, [r14+10h]; Identity
0x1800060c8  mov     ecx, [rbp+arg_8]; SessionHandle
0x1800060cb  mov     r9b, 0FFh; SubFactor
0x1800060ce  call    cs:__imp_WinBioDeleteTemplate
0x1800060d4  mov     rax, [rbp+UnitCount]
0x1800060d8  add     rbx, r13
0x1800060db  cmp     rbx, rax
0x1800060de  jb      short loc_1800060AF
0x1800060e0  mov     ecx, [rbp+arg_8]; SessionHandle
0x1800060e3  call    cs:__imp_WinBioCloseSession
0x1800060e9  mov     rcx, [rbp+UnitSchemaArray]; Address
0x1800060ed  call    cs:__imp_WinBioFree
0x1800060f3  add     edi, edi
0x1800060f5  jmp     loc_180005FD7
0x1800060fa  sub     cs:dword_1800105B4, r13d
0x180006101  mov     eax, esi
0x180006103  add     rsp, 40h
0x180006107  pop     r15
0x180006109  pop     r14
0x18000610b  pop     r13
0x18000610d  pop     rdi
0x18000610e  pop     rsi
0x18000610f  pop     rbx
0x180006110  pop     rbp
0x180006111  retn
```
