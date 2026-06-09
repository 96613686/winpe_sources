# UbpmUtilsRemoveProcessPrivileges(void *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x18002ac90`
- end: `0x18002add0`
- name: `?UbpmUtilsRemoveProcessPrivileges@@YAKPEAX_K11PEA_K@Z`
- size: `320`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f284`

## callees

- `0x18000fbf0`
- `0x18002ac90`
- `0x18002add8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002ad67`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002ad67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adbd`

## pseudocode

```c
__int64 __fastcall UbpmUtilsRemoveProcessPrivileges(
        HANDLE TokenHandle,
        __int64 a2,
        unsigned __int64 *a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v5; // r14
  DWORD ProcessPrivileges; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  PTOKEN_PRIVILEGES v14; // rbx
  DWORD LastError; // edi
  __int64 v17; // r11
  DWORD LowPart; // ecx
  __int64 v19; // rcx
  PTOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp+10h] BYREF

  v5 = a5;
  NewState = 0;
  *a5 = 0;
  ProcessPrivileges = UbpmUtilsGetProcessPrivileges(TokenHandle, &NewState, a3);
  v14 = NewState;
  LastError = ProcessPrivileges;
  if ( !ProcessPrivileges )
  {
    v12 = 0;
    v13 = 0;
    v17 = a2;
    if ( NewState->PrivilegeCount )
    {
      do
      {
        LowPart = v14->Privileges[v13].Luid.LowPart;
        v11 = 1LL << LowPart;
        if ( v17 && (v11 & a2) == 0 || (v11 & (unsigned __int64)a3) != 0 )
        {
          if ( LowPart != 23 || v14->Privileges[v13].Luid.HighPart )
          {
            v19 = v12;
            v12 = (unsigned int)(v12 + 1);
            v14->Privileges[v19].Attributes = 4;
            v14->Privileges[v19].Luid = v14->Privileges[v13].Luid;
          }
          else
          {
            *v5 |= v11;
          }
        }
        else
        {
          *v5 |= v11;
          a2 &= ~v11;
          a4 &= ~v11;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < v14->PrivilegeCount );
    }
    if ( a2 || a4 )
    {
      LastError = 87;
    }
    else if ( (_DWORD)v12 && (v14->PrivilegeCount = v12, !AdjustTokenPrivileges(TokenHandle, 0, v14, 0, 0, 0)) )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
    }
  }
  UBPM_MIDL_user_free(v14, v11, v12, v13);
  return LastError;
}

```

## disassembly

```asm
0x18002ac90  mov     rax, rsp
0x18002ac93  mov     [rax+8], rbx
0x18002ac97  mov     [rax+18h], rbp
0x18002ac9b  push    rsi
0x18002ac9c  push    rdi
0x18002ac9d  push    r12
0x18002ac9f  push    r14
0x18002aca1  push    r15
0x18002aca3  sub     rsp, 30h
0x18002aca7  mov     r14, [rsp+58h+arg_20]
0x18002acaf  mov     rsi, rdx
0x18002acb2  lea     rdx, [rax+10h]; struct _TOKEN_PRIVILEGES **
0x18002acb6  mov     qword ptr [rax+10h], 0
0x18002acbe  mov     rbp, r9
0x18002acc1  mov     r12, r8
0x18002acc4  mov     r15, rcx
0x18002acc7  mov     qword ptr [r14], 0
0x18002acce  call    ?UbpmUtilsGetProcessPrivileges@@YAKPEAXPEAPEAU_TOKEN_PRIVILEGES@@PEA_K@Z; UbpmUtilsGetProcessPrivileges(void *,_TOKEN_PRIVILEGES * *,unsigned __int64 *)
0x18002acd3  mov     rbx, [rsp+58h+NewState]
0x18002acd8  mov     edi, eax
0x18002acda  test    eax, eax
0x18002acdc  jz      short loc_18002AD00
0x18002acde  mov     rcx, rbx
0x18002ace1  call    UBPM_MIDL_user_free
0x18002ace6  mov     rbx, [rsp+58h+arg_0]
0x18002aceb  mov     eax, edi
0x18002aced  mov     rbp, [rsp+58h+arg_10]
0x18002acf2  add     rsp, 30h
0x18002acf6  pop     r15
0x18002acf8  pop     r14
0x18002acfa  pop     r12
0x18002acfc  pop     rdi
0x18002acfd  pop     rsi
0x18002acfe  retn
0x18002ad00  xor     r8d, r8d
0x18002ad03  xor     r9d, r9d
0x18002ad06  mov     r11, rsi
0x18002ad09  cmp     [rbx], r8d
0x18002ad0c  jbe     short loc_18002AD40
0x18002ad0e  lea     r10, [r9+r9*2]
0x18002ad12  mov     edx, 1
0x18002ad17  mov     ecx, [rbx+r10*4+4]
0x18002ad1c  shl     rdx, cl
0x18002ad1f  test    r11, r11
0x18002ad22  jnz     short loc_18002AD7E
0x18002ad24  test    r12, rdx
0x18002ad27  jnz     short loc_18002AD83
0x18002ad29  or      [r14], rdx
0x18002ad2c  mov     rax, rdx
0x18002ad2f  not     rax
0x18002ad32  and     rsi, rax
0x18002ad35  and     rbp, rax
0x18002ad38  inc     r9d
0x18002ad3b  cmp     r9d, [rbx]
0x18002ad3e  jb      short loc_18002AD0E
0x18002ad40  test    rsi, rsi
0x18002ad43  jnz     short loc_18002ADA3
0x18002ad45  test    rbp, rbp
0x18002ad48  jnz     short loc_18002ADA3
0x18002ad4a  test    r8d, r8d
0x18002ad4d  jz      short loc_18002AD77
0x18002ad4f  mov     [rbx], r8d
0x18002ad52  xor     r9d, r9d; BufferLength
0x18002ad55  mov     r8, rbx; NewState
0x18002ad58  mov     [rsp+58h+ReturnLength], rbp; ReturnLength
0x18002ad5d  xor     edx, edx; DisableAllPrivileges
0x18002ad5f  mov     [rsp+58h+PreviousState], rbp; PreviousState
0x18002ad64  mov     rcx, r15; TokenHandle
0x18002ad67  call    cs:__imp_AdjustTokenPrivileges
0x18002ad6e  nop     dword ptr [rax+rax+00h]
0x18002ad73  test    eax, eax
0x18002ad75  jz      short loc_18002ADBD
0x18002ad77  xor     edi, edi
0x18002ad79  jmp     loc_18002ACDE
0x18002ad7e  test    rsi, rdx
0x18002ad81  jnz     short loc_18002AD24
0x18002ad83  cmp     ecx, 17h
0x18002ad86  jz      short loc_18002ADAD
0x18002ad88  lea     rcx, [r8+r8*2]
0x18002ad8c  inc     r8d
0x18002ad8f  mov     dword ptr [rbx+rcx*4+0Ch], 4
0x18002ad97  mov     rax, [rbx+r10*4+4]
0x18002ad9c  mov     [rbx+rcx*4+4], rax
0x18002ada1  jmp     short loc_18002AD38
0x18002ada3  mov     edi, 57h ; 'W'
0x18002ada8  jmp     loc_18002ACDE
0x18002adad  cmp     dword ptr [rbx+r10*4+8], 0
0x18002adb3  jnz     short loc_18002AD88
0x18002adb5  or      [r14], rdx
0x18002adb8  jmp     loc_18002AD38
0x18002adbd  call    cs:__imp_GetLastError
0x18002adc4  nop     dword ptr [rax+rax+00h]
0x18002adc9  mov     edi, eax
0x18002adcb  jmp     loc_18002ACDE
```
