# BaseSrvUpdateDOSEntry

- ea: `0x18000c088`
- end: `0x18000c248`
- name: `BaseSrvUpdateDOSEntry`
- size: `448`
- prototype: `__int64 __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000c250`

## callees

- `0x180009114`
- `0x180009698`
- `0x180009788`
- `0x18000a54c`
- `0x18000a614`
- `0x18000a8fc`
- `0x18000be3c`
- `0x18000c088`
- `0x18000c5e4`

## import_xrefs

- `ntdll!NtClose` at `0x18000c160`
- `ntdll!NtClose` at `0x18000c1a6`
- `ntdll!NtClose` at `0x18000c160`
- `ntdll!NtClose` at `0x18000c1a6`
- `ntdll!RtlEnterCriticalSection` at `0x18000c0b2`
- `ntdll!RtlEnterCriticalSection` at `0x18000c0b2`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c22e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c22e`
- `ntdll!NtDuplicateObject` at `0x18000c13e`
- `ntdll!NtDuplicateObject` at `0x18000c13e`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateDOSEntry(unsigned int *a1, int a2)
{
  __int64 v4; // rcx
  int ConsoleRecordDosSesId; // eax
  NTSTATUS v6; // esi
  HANDLE *v7; // rbx
  __int64 v8; // r14
  HANDLE v9; // rcx
  PVOID P; // [rsp+70h] [rbp+30h] BYREF
  __int64 v12; // [rsp+80h] [rbp+40h] BYREF
  __int64 v13; // [rsp+88h] [rbp+48h] BYREF

  P = 0;
  v13 = 0;
  v12 = 0;
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
        v7 = (HANDLE *)P;
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
      *((_QWORD *)a1 + 3) = 0;
      if ( a1[1] == 16 )
      {
        v6 = BaseSrvDupStandardHandles(v7[2]);
        if ( v6 >= 0 && !*((_DWORD *)v7 + 13) )
        {
          v6 = BaseSrvCreatePairWaitHandles(&v13, &v12);
          if ( v6 < 0 )
          {
            BaseSrvCloseStandardHandles(v7[2]);
          }
          else
          {
            *(_QWORD *)(v8 + 16) = v12;
            *(_QWORD *)(v8 + 24) = v13;
            *((_QWORD *)a1 + 3) = v12;
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
0x18000c088  push    rbp
0x18000c08a  push    rbx
0x18000c08b  push    rsi
0x18000c08c  push    rdi
0x18000c08d  push    r14
0x18000c08f  mov     rbp, rsp
0x18000c092  sub     rsp, 40h
0x18000c096  and     [rbp+P], 0
0x18000c09b  mov     rdi, rcx
0x18000c09e  and     [rbp+arg_18], 0
0x18000c0a3  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c0aa  and     [rbp+arg_10], 0
0x18000c0af  mov     r14d, edx
0x18000c0b2  call    cs:__imp_RtlEnterCriticalSection
0x18000c0b9  nop     dword ptr [rax+rax+00h]
0x18000c0be  mov     ecx, [rdi]
0x18000c0c0  lea     rdx, [rbp+P]
0x18000c0c4  test    ecx, ecx
0x18000c0c6  jz      short loc_18000C0CF
0x18000c0c8  call    GetConsoleRecordDosSesId
0x18000c0cd  jmp     short loc_18000C0D8
0x18000c0cf  mov     rcx, [rdi+8]
0x18000c0d3  call    BaseSrvGetConsoleRecord
0x18000c0d8  mov     esi, eax
0x18000c0da  test    eax, eax
0x18000c0dc  js      loc_18000C227
0x18000c0e2  mov     rbx, [rbp+P]
0x18000c0e6  cmp     r14d, [rbx+30h]
0x18000c0ea  jz      short loc_18000C0F6
0x18000c0ec  mov     esi, 0C000000Dh
0x18000c0f1  jmp     loc_18000C227
0x18000c0f6  movzx   ecx, word ptr [rdi+20h]
0x18000c0fa  mov     r14, [rbx+48h]
0x18000c0fe  test    ecx, ecx
0x18000c100  jz      short loc_18000C156
0x18000c102  cmp     ecx, 1
0x18000c105  jnz     loc_18000C1BA
0x18000c10b  mov     rax, gs:70h
0x18000c114  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x18000c118  mov     rbx, [rbp+P]
0x18000c11c  mov     rdx, [rdi+10h]; SourceHandle
0x18000c120  mov     [rsp+40h+Options], 2; Options
0x18000c128  mov     rcx, [rax+38h]
0x18000c12c  and     [rsp+40h+var_18], 0
0x18000c131  lea     r9, [rbx+10h]; TargetHandle
0x18000c135  and     [rsp+40h+var_20], 0
0x18000c13a  mov     rcx, [rcx+50h]; SourceProcessHandle
0x18000c13e  call    cs:__imp_NtDuplicateObject
0x18000c145  nop     dword ptr [rax+rax+00h]
0x18000c14a  mov     esi, eax
0x18000c14c  test    eax, eax
0x18000c14e  js      loc_18000C227
0x18000c154  jmp     short loc_18000C1BA
0x18000c156  test    byte ptr [rdi+22h], 6
0x18000c15a  jz      short loc_18000C171
0x18000c15c  mov     rcx, [r14+18h]; Handle
0x18000c160  call    cs:__imp_NtClose
0x18000c167  nop     dword ptr [rax+rax+00h]
0x18000c16c  and     qword ptr [r14+18h], 0
0x18000c171  test    byte ptr [rdi+22h], 1
0x18000c175  jnz     short loc_18000C17D
0x18000c177  test    byte ptr [rdi+22h], 2
0x18000c17b  jz      short loc_18000C1BA
0x18000c17d  mov     rdx, r14
0x18000c180  mov     rcx, rbx
0x18000c183  call    BaseSrvRemoveDOSRecord
0x18000c188  mov     rcx, r14
0x18000c18b  call    BaseSrvFreeDOSRecord
0x18000c190  cmp     qword ptr [rbx+48h], 0
0x18000c195  jnz     short loc_18000C1BA
0x18000c197  test    byte ptr [rdi+22h], 2
0x18000c19b  jz      short loc_18000C1B2
0x18000c19d  mov     rcx, [rbx+10h]; Handle
0x18000c1a1  test    rcx, rcx
0x18000c1a4  jz      short loc_18000C1B2
0x18000c1a6  call    cs:__imp_NtClose
0x18000c1ad  nop     dword ptr [rax+rax+00h]
0x18000c1b2  mov     rcx, rbx; P
0x18000c1b5  call    BaseSrvFreeConsoleRecord
0x18000c1ba  cmp     word ptr [rdi+20h], 1
0x18000c1bf  jnz     short loc_18000C227
0x18000c1c1  and     qword ptr [r14+10h], 0
0x18000c1c6  and     qword ptr [r14+18h], 0
0x18000c1cb  and     qword ptr [rdi+18h], 0
0x18000c1d0  cmp     dword ptr [rdi+4], 10h
0x18000c1d4  jnz     short loc_18000C227
0x18000c1d6  mov     rcx, [rbx+10h]; SourceProcessHandle
0x18000c1da  mov     rdx, r14
0x18000c1dd  call    BaseSrvDupStandardHandles
0x18000c1e2  mov     esi, eax
0x18000c1e4  test    eax, eax
0x18000c1e6  js      short loc_18000C227
0x18000c1e8  cmp     dword ptr [rbx+34h], 0
0x18000c1ec  jnz     short loc_18000C227
0x18000c1ee  lea     rdx, [rbp+arg_10]
0x18000c1f2  lea     rcx, [rbp+arg_18]
0x18000c1f6  call    BaseSrvCreatePairWaitHandles
0x18000c1fb  mov     esi, eax
0x18000c1fd  test    eax, eax
0x18000c1ff  js      short loc_18000C21B
0x18000c201  mov     rax, [rbp+arg_10]
0x18000c205  mov     [r14+10h], rax
0x18000c209  mov     rax, [rbp+arg_18]
0x18000c20d  mov     [r14+18h], rax
0x18000c211  mov     rax, [rbp+arg_10]
0x18000c215  mov     [rdi+18h], rax
0x18000c219  jmp     short loc_18000C227
0x18000c21b  mov     rcx, [rbx+10h]; SourceProcessHandle
0x18000c21f  mov     rdx, r14
0x18000c222  call    BaseSrvCloseStandardHandles
0x18000c227  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c22e  call    cs:__imp_RtlLeaveCriticalSection
0x18000c235  nop     dword ptr [rax+rax+00h]
0x18000c23a  mov     eax, esi
0x18000c23c  add     rsp, 40h
0x18000c240  pop     r14
0x18000c242  pop     rdi
0x18000c243  pop     rsi
0x18000c244  pop     rbx
0x18000c245  pop     rbp
0x18000c246  retn
```
