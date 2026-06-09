# BaseSrvUpdateDOSEntry

- ea: `0x18000c434`
- end: `0x18000c612`
- name: `BaseSrvUpdateDOSEntry`
- size: `478`
- prototype: `__int64 __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000c620`

## callees

- `0x1800093e8`
- `0x18000996c`
- `0x180009a60`
- `0x18000a7d0`
- `0x18000a898`
- `0x18000ab84`
- `0x18000c128`
- `0x18000c434`
- `0x18000c9c0`

## import_xrefs

- `ntdll!NtClose` at `0x18000c517`
- `ntdll!NtClose` at `0x18000c560`
- `ntdll!NtClose` at `0x18000c517`
- `ntdll!NtClose` at `0x18000c560`
- `ntdll!RtlEnterCriticalSection` at `0x18000c466`
- `ntdll!RtlEnterCriticalSection` at `0x18000c466`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c5f6`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c5f6`
- `ntdll!NtDuplicateObject` at `0x18000c4f5`
- `ntdll!NtDuplicateObject` at `0x18000c4f5`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateDOSEntry(unsigned int *a1, int a2)
{
  __int64 v4; // rcx
  int ConsoleRecordDosSesId; // eax
  NTSTATUS v6; // ebp
  HANDLE *v7; // rdi
  __int64 v8; // rsi
  HANDLE v9; // rcx
  bool v10; // zf
  PVOID P; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  P = 0;
  v14 = 0;
  v13 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  v4 = *a1;
  if ( (_DWORD)v4 )
    ConsoleRecordDosSesId = GetConsoleRecordDosSesId(v4, &P);
  else
    ConsoleRecordDosSesId = BaseSrvGetConsoleRecord(*((_QWORD *)a1 + 1), &P);
  v6 = ConsoleRecordDosSesId;
  if ( ConsoleRecordDosSesId >= 0 )
  {
    v7 = (HANDLE *)P;
    if ( a2 != *((_DWORD *)P + 12) )
    {
      v6 = -1073741811;
      goto LABEL_27;
    }
    v8 = *((_QWORD *)P + 9);
    if ( *((_WORD *)a1 + 16) )
    {
      if ( *((_WORD *)a1 + 16) == 1 )
      {
        v6 = NtDuplicateObject(
               *(HANDLE *)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL),
               *((HANDLE *)a1 + 2),
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               (PHANDLE)P + 2,
               0,
               0,
               2u);
        if ( v6 < 0 )
          goto LABEL_27;
      }
    }
    else
    {
      if ( (*((_BYTE *)a1 + 34) & 6) != 0 )
      {
        NtClose(*(HANDLE *)(v8 + 24));
        *(_QWORD *)(v8 + 24) = 0;
      }
      if ( (*((_BYTE *)a1 + 34) & 1) != 0 || (*((_BYTE *)a1 + 34) & 2) != 0 )
      {
        BaseSrvRemoveDOSRecord(v7, v8);
        BaseSrvFreeDOSRecord(v8);
        if ( !v7[9] )
        {
          if ( (*((_BYTE *)a1 + 34) & 2) != 0 )
          {
            v9 = v7[2];
            if ( v9 )
              NtClose(v9);
          }
          BaseSrvFreeConsoleRecord(v7);
        }
      }
    }
    if ( *((_WORD *)a1 + 16) == 1 )
    {
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      v10 = a1[1] == 16;
      *((_QWORD *)a1 + 3) = 0;
      if ( v10 )
      {
        v6 = BaseSrvDupStandardHandles(v7[2]);
        if ( v6 >= 0 && !*((_DWORD *)v7 + 13) )
        {
          v6 = BaseSrvCreatePairWaitHandles(&v14, &v13);
          if ( v6 < 0 )
          {
            BaseSrvCloseStandardHandles(v7[2]);
          }
          else
          {
            *(_QWORD *)(v8 + 16) = v13;
            *(_QWORD *)(v8 + 24) = v14;
            *((_QWORD *)a1 + 3) = v13;
          }
        }
      }
    }
  }
LABEL_27:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c434  mov     rax, rsp
0x18000c437  mov     [rax+10h], rbx
0x18000c43b  push    rbp
0x18000c43c  push    rsi
0x18000c43d  push    rdi
0x18000c43e  sub     rsp, 40h
0x18000c442  mov     rbx, rcx
0x18000c445  mov     qword ptr [rax+8], 0
0x18000c44d  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c454  mov     qword ptr [rax+20h], 0
0x18000c45c  mov     esi, edx
0x18000c45e  mov     qword ptr [rax+18h], 0
0x18000c466  call    cs:__imp_RtlEnterCriticalSection
0x18000c46d  nop     dword ptr [rax+rax+00h]
0x18000c472  mov     ecx, [rbx]
0x18000c474  lea     rdx, [rsp+58h+P]
0x18000c479  test    ecx, ecx
0x18000c47b  jz      short loc_18000C484
0x18000c47d  call    GetConsoleRecordDosSesId
0x18000c482  jmp     short loc_18000C48D
0x18000c484  mov     rcx, [rbx+8]
0x18000c488  call    BaseSrvGetConsoleRecord
0x18000c48d  mov     ebp, eax
0x18000c48f  test    eax, eax
0x18000c491  js      loc_18000C5EF
0x18000c497  mov     rdi, [rsp+58h+P]
0x18000c49c  cmp     esi, [rdi+30h]
0x18000c49f  jz      short loc_18000C4AB
0x18000c4a1  mov     ebp, 0C000000Dh
0x18000c4a6  jmp     loc_18000C5EF
0x18000c4ab  movzx   ecx, word ptr [rbx+20h]
0x18000c4af  mov     rsi, [rdi+48h]
0x18000c4b3  test    ecx, ecx
0x18000c4b5  jz      short loc_18000C50D
0x18000c4b7  cmp     ecx, 1
0x18000c4ba  jnz     loc_18000C574
0x18000c4c0  mov     rax, gs:70h
0x18000c4c9  lea     r9, [rdi+10h]; TargetHandle
0x18000c4cd  mov     rdx, [rbx+10h]; SourceHandle
0x18000c4d1  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x18000c4d5  mov     [rsp+58h+Options], 2; Options
0x18000c4dd  mov     [rsp+58h+HandleAttributes], 0; HandleAttributes
0x18000c4e5  mov     rcx, [rax+38h]
0x18000c4e9  mov     [rsp+58h+DesiredAccess], 0; DesiredAccess
0x18000c4f1  mov     rcx, [rcx+50h]; SourceProcessHandle
0x18000c4f5  call    cs:__imp_NtDuplicateObject
0x18000c4fc  nop     dword ptr [rax+rax+00h]
0x18000c501  mov     ebp, eax
0x18000c503  test    eax, eax
0x18000c505  js      loc_18000C5EF
0x18000c50b  jmp     short loc_18000C574
0x18000c50d  test    byte ptr [rbx+22h], 6
0x18000c511  jz      short loc_18000C52B
0x18000c513  mov     rcx, [rsi+18h]; Handle
0x18000c517  call    cs:__imp_NtClose
0x18000c51e  nop     dword ptr [rax+rax+00h]
0x18000c523  mov     qword ptr [rsi+18h], 0
0x18000c52b  test    byte ptr [rbx+22h], 1
0x18000c52f  jnz     short loc_18000C537
0x18000c531  test    byte ptr [rbx+22h], 2
0x18000c535  jz      short loc_18000C574
0x18000c537  mov     rdx, rsi
0x18000c53a  mov     rcx, rdi
0x18000c53d  call    BaseSrvRemoveDOSRecord
0x18000c542  mov     rcx, rsi
0x18000c545  call    BaseSrvFreeDOSRecord
0x18000c54a  cmp     qword ptr [rdi+48h], 0
0x18000c54f  jnz     short loc_18000C574
0x18000c551  test    byte ptr [rbx+22h], 2
0x18000c555  jz      short loc_18000C56C
0x18000c557  mov     rcx, [rdi+10h]; Handle
0x18000c55b  test    rcx, rcx
0x18000c55e  jz      short loc_18000C56C
0x18000c560  call    cs:__imp_NtClose
0x18000c567  nop     dword ptr [rax+rax+00h]
0x18000c56c  mov     rcx, rdi; P
0x18000c56f  call    BaseSrvFreeConsoleRecord
0x18000c574  cmp     word ptr [rbx+20h], 1
0x18000c579  jnz     short loc_18000C5EF
0x18000c57b  mov     qword ptr [rsi+10h], 0
0x18000c583  mov     qword ptr [rsi+18h], 0
0x18000c58b  cmp     dword ptr [rbx+4], 10h
0x18000c58f  mov     qword ptr [rbx+18h], 0
0x18000c597  jnz     short loc_18000C5EF
0x18000c599  mov     rcx, [rdi+10h]; SourceProcessHandle
0x18000c59d  mov     rdx, rsi
0x18000c5a0  call    BaseSrvDupStandardHandles
0x18000c5a5  mov     ebp, eax
0x18000c5a7  test    eax, eax
0x18000c5a9  js      short loc_18000C5EF
0x18000c5ab  cmp     dword ptr [rdi+34h], 0
0x18000c5af  jnz     short loc_18000C5EF
0x18000c5b1  lea     rdx, [rsp+58h+arg_10]
0x18000c5b6  lea     rcx, [rsp+58h+arg_18]
0x18000c5bb  call    BaseSrvCreatePairWaitHandles
0x18000c5c0  mov     ebp, eax
0x18000c5c2  test    eax, eax
0x18000c5c4  js      short loc_18000C5E3
0x18000c5c6  mov     rax, [rsp+58h+arg_10]
0x18000c5cb  mov     [rsi+10h], rax
0x18000c5cf  mov     rax, [rsp+58h+arg_18]
0x18000c5d4  mov     [rsi+18h], rax
0x18000c5d8  mov     rax, [rsp+58h+arg_10]
0x18000c5dd  mov     [rbx+18h], rax
0x18000c5e1  jmp     short loc_18000C5EF
0x18000c5e3  mov     rcx, [rdi+10h]; SourceProcessHandle
0x18000c5e7  mov     rdx, rsi
0x18000c5ea  call    BaseSrvCloseStandardHandles
0x18000c5ef  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c5f6  call    cs:__imp_RtlLeaveCriticalSection
0x18000c5fd  nop     dword ptr [rax+rax+00h]
0x18000c602  mov     rbx, [rsp+58h+arg_8]
0x18000c607  mov     eax, ebp
0x18000c609  add     rsp, 40h
0x18000c60d  pop     rdi
0x18000c60e  pop     rsi
0x18000c60f  pop     rbp
0x18000c610  retn
```
