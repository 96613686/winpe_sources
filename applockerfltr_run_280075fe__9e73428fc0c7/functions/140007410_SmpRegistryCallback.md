# SmpRegistryCallback

- ea: `0x140007410`
- end: `0x1400076e8`
- name: `SmpRegistryCallback`
- size: `728`
- prototype: `EX_CALLBACK_FUNCTION`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, registry_config, installer_update`

## callees

- `0x14000118c`
- `0x1400012c8`
- `0x1400015e0`
- `0x140001674`
- `0x140007410`
- `0x140007cec`
- `0x140007e00`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x14000764f`
- `ntoskrnl!SeLocateProcessImageName` at `0x14000764f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000768c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000768c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400076c1`
- `ntoskrnl!CmCallbackGetKeyObjectID` at `0x1400074fe`
- `ntoskrnl!CmCallbackGetKeyObjectID` at `0x1400074fe`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140007522`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140007540`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000755e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140007522`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140007540`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000755e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400075a1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400075a1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000747b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000747b`

## pseudocode

```c
__int64 __fastcall SmpRegistryCallback(PVOID CallbackContext, PVOID Argument1, PVOID Argument2)
{
  _QWORD *v4; // rsi
  void *v6; // rdi
  unsigned __int16 v7; // cx
  __int64 v8; // rdx
  bool v9; // zf
  NTSTATUS KeyObjectID; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r15
  struct _KPROCESS *CurrentProcess; // r12
  int v15; // eax
  PVOID v16; // rdi
  int v17; // eax
  char v18; // r14
  _DWORD *v19; // r14
  int v20; // eax
  NTSTATUS v21; // eax
  PUNICODE_STRING v22; // r8
  int v23; // [rsp+20h] [rbp-40h] BYREF
  PCUNICODE_STRING ObjectName; // [rsp+28h] [rbp-38h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+30h] [rbp-30h] BYREF
  PVOID v26; // [rsp+38h] [rbp-28h] BYREF
  PVOID P; // [rsp+40h] [rbp-20h] BYREF
  __int128 v28; // [rsp+48h] [rbp-18h] BYREF
  char v29; // [rsp+A8h] [rbp+48h] BYREF

  ObjectName = 0;
  P = 0;
  v4 = 0;
  pImageFileName = 0;
  v26 = 0;
  v23 = 0;
  v29 = 0;
  v28 = 0;
  if ( (_DWORD)Argument1 != 1 )
    return 0;
  if ( (unsigned int)(*((_DWORD *)Argument2 + 5) - 1) > 1 )
    goto LABEL_42;
  v6 = *(void **)Argument2;
  if ( !RtlEqualUnicodeString(*((PCUNICODE_STRING *)Argument2 + 1), &String2, 1u) )
    goto LABEL_42;
  if ( *((_DWORD *)Argument2 + 8) > 0xFFFFu )
    goto LABEL_42;
  v7 = *((_WORD *)Argument2 + 16);
  v8 = *((_QWORD *)Argument2 + 3);
  *((_QWORD *)&v28 + 1) = v8;
  WORD1(v28) = v7;
  LOWORD(v28) = v7;
  if ( (v7 & 1) != 0 || v7 < 4u )
    goto LABEL_42;
  LOWORD(v28) = v7;
  do
  {
    if ( *(_WORD *)(v8 + 2 * ((unsigned __int64)v7 >> 1) - 2) )
      break;
    v9 = v7 == 2;
    v7 -= 2;
    LOWORD(v28) = v7;
  }
  while ( !v9 );
  if ( v7 < 4u )
  {
LABEL_42:
    KeyObjectID = 0;
    goto LABEL_43;
  }
  KeyObjectID = CmCallbackGetKeyObjectID(&Cookie, v6, 0, &ObjectName);
  if ( KeyObjectID >= 0 )
  {
    if ( RtlPrefixUnicodeString(&String1, ObjectName, 1u)
      || RtlPrefixUnicodeString(&stru_140003160, ObjectName, 1u)
      || RtlPrefixUnicodeString(&stru_140003170, ObjectName, 1u)
      && ((unsigned __int8)SmpFindSubStr(v11, ObjectName, L"fh")
       || (unsigned __int8)SmpFindSubStr(v12, ObjectName, &qword_140003140)) )
    {
      v13 = 0;
      CurrentProcess = IoGetCurrentProcess();
      v15 = SmCheckProcessSessionOrigin(CurrentProcess, &v23, &v26);
      v16 = v26;
      KeyObjectID = v15;
      if ( v15 < 0 || !v26 )
      {
        v17 = SmCheckOrigin(CurrentProcess, &v29, &P);
        v4 = P;
        KeyObjectID = v17;
        v18 = v29;
        if ( v17 >= 0 && v29 || (v13 = SmCheckProcessOrigin(CurrentProcess), v18) )
        {
          if ( v4 )
            goto LABEL_27;
        }
        if ( !v13 && !v16 )
        {
LABEL_38:
          if ( v4 )
            ExFreePoolWithTag(v4, 0x41746D73u);
          if ( v16 )
            ExFreePoolWithTag(v16, 0x53746D73u);
          goto LABEL_43;
        }
        if ( v4 )
        {
LABEL_27:
          v19 = **(_DWORD ***)(v4[1] + 32LL);
          goto LABEL_32;
        }
        if ( v13 )
        {
          v19 = *(_DWORD **)(v13 + 32);
LABEL_32:
          v20 = v19[2];
          if ( (v20 & 0xFFFFFFFC) == 0 && v20 != 2 )
          {
            v21 = SeLocateProcessImageName(CurrentProcess, &pImageFileName);
            v22 = (PUNICODE_STRING)&qword_140003130;
            KeyObjectID = v21;
            if ( v21 >= 0 )
              v22 = pImageFileName;
            SmRegisterUninstallStringWithSessionOrigin(v19, &v28, v22);
          }
          SmReleaseOriginProcessData(v13);
          goto LABEL_38;
        }
      }
      v19 = 0;
      if ( v16 )
        v19 = v16;
      goto LABEL_32;
    }
    goto LABEL_42;
  }
LABEL_43:
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  return (unsigned int)KeyObjectID;
}

```

## disassembly

```asm
0x140007410  mov     [rsp-38h+arg_0], rbx
0x140007415  push    rbp
0x140007416  push    rsi
0x140007417  push    rdi
0x140007418  push    r12
0x14000741a  push    r13
0x14000741c  push    r14
0x14000741e  push    r15
0x140007420  mov     rbp, rsp
0x140007423  sub     rsp, 60h
0x140007427  xor     r13d, r13d
0x14000742a  xorps   xmm0, xmm0
0x14000742d  mov     [rbp+ObjectName], r13
0x140007431  mov     rbx, r8
0x140007434  mov     [rbp+P], r13
0x140007438  mov     esi, r13d
0x14000743b  mov     [rbp+pImageFileName], r13
0x14000743f  mov     [rbp+var_28], r13
0x140007443  mov     [rbp+var_40], r13d
0x140007447  mov     [rbp+arg_8], r13b
0x14000744b  movups  [rbp+var_18], xmm0
0x14000744f  cmp     edx, 1
0x140007452  jz      short loc_14000745B
0x140007454  xor     eax, eax
0x140007456  jmp     loc_1400076CF
0x14000745b  mov     eax, [r8+14h]
0x14000745f  dec     eax
0x140007461  cmp     eax, 1
0x140007464  ja      loc_1400076B3
0x14000746a  mov     rdi, [r8]
0x14000746d  lea     rdx, String2; String2
0x140007474  mov     rcx, [rbx+8]; String1
0x140007478  mov     r8b, 1; CaseInSensitive
0x14000747b  call    cs:__imp_RtlEqualUnicodeString
0x140007482  nop     dword ptr [rax+rax+00h]
0x140007487  test    al, al
0x140007489  jz      loc_1400076B3
0x14000748f  cmp     dword ptr [rbx+20h], 0FFFFh
0x140007496  ja      loc_1400076B3
0x14000749c  movzx   ecx, word ptr [rbx+20h]
0x1400074a0  mov     rdx, [rbx+18h]
0x1400074a4  mov     qword ptr [rbp+var_18+8], rdx
0x1400074a8  mov     word ptr [rbp+var_18+2], cx
0x1400074ac  mov     word ptr [rbp+var_18], cx
0x1400074b0  test    cl, 1
0x1400074b3  jnz     loc_1400076B3
0x1400074b9  cmp     cx, 4
0x1400074bd  jb      loc_1400076B3
0x1400074c3  mov     word ptr [rbp+var_18], cx
0x1400074c7  movzx   eax, cx
0x1400074ca  shr     rax, 1
0x1400074cd  cmp     [rdx+rax*2-2], r13w
0x1400074d3  jnz     short loc_1400074E3
0x1400074d5  mov     eax, 0FFFEh
0x1400074da  add     cx, ax
0x1400074dd  mov     word ptr [rbp+var_18], cx
0x1400074e1  jnz     short loc_1400074C7
0x1400074e3  cmp     cx, 4
0x1400074e7  jb      loc_1400076B3
0x1400074ed  lea     r9, [rbp+ObjectName]; ObjectName
0x1400074f1  xor     r8d, r8d; ObjectID
0x1400074f4  mov     rdx, rdi; Object
0x1400074f7  lea     rcx, Cookie; Cookie
0x1400074fe  call    cs:__imp_CmCallbackGetKeyObjectID
0x140007505  nop     dword ptr [rax+rax+00h]
0x14000750a  mov     ebx, eax
0x14000750c  test    eax, eax
0x14000750e  js      loc_1400076B6
0x140007514  mov     rdx, [rbp+ObjectName]; String2
0x140007518  lea     rcx, String1; String1
0x14000751f  mov     r8b, 1; CaseInSensitive
0x140007522  call    cs:__imp_RtlPrefixUnicodeString
0x140007529  nop     dword ptr [rax+rax+00h]
0x14000752e  test    al, al
0x140007530  jnz     short loc_14000759E
0x140007532  mov     rdx, [rbp+ObjectName]; String2
0x140007536  lea     rcx, stru_140003160; String1
0x14000753d  mov     r8b, 1; CaseInSensitive
0x140007540  call    cs:__imp_RtlPrefixUnicodeString
0x140007547  nop     dword ptr [rax+rax+00h]
0x14000754c  test    al, al
0x14000754e  jnz     short loc_14000759E
0x140007550  mov     rdx, [rbp+ObjectName]; String2
0x140007554  lea     rcx, stru_140003170; String1
0x14000755b  mov     r8b, 1; CaseInSensitive
0x14000755e  call    cs:__imp_RtlPrefixUnicodeString
0x140007565  nop     dword ptr [rax+rax+00h]
0x14000756a  test    al, al
0x14000756c  jz      loc_1400076B3
0x140007572  mov     rdx, [rbp+ObjectName]
0x140007576  lea     r8, aFh; "fh"
0x14000757d  call    SmpFindSubStr
0x140007582  test    al, al
0x140007584  jnz     short loc_14000759E
0x140007586  mov     rdx, [rbp+ObjectName]
0x14000758a  lea     r8, qword_140003140
0x140007591  call    SmpFindSubStr
0x140007596  test    al, al
0x140007598  jz      loc_1400076B3
0x14000759e  mov     r15, r13
0x1400075a1  call    cs:__imp_IoGetCurrentProcess
0x1400075a8  nop     dword ptr [rax+rax+00h]
0x1400075ad  mov     rcx, rax
0x1400075b0  lea     r8, [rbp+var_28]
0x1400075b4  lea     rdx, [rbp+var_40]
0x1400075b8  mov     r12, rax
0x1400075bb  call    SmCheckProcessSessionOrigin
0x1400075c0  mov     rdi, [rbp+var_28]
0x1400075c4  mov     ebx, eax
0x1400075c6  test    eax, eax
0x1400075c8  js      short loc_1400075CF
0x1400075ca  test    rdi, rdi
0x1400075cd  jnz     short loc_14000762E
0x1400075cf  lea     r8, [rbp+P]
0x1400075d3  mov     rcx, r12
0x1400075d6  lea     rdx, [rbp+arg_8]
0x1400075da  call    SmCheckOrigin
0x1400075df  mov     rsi, [rbp+P]
0x1400075e3  mov     ebx, eax
0x1400075e5  mov     r14b, [rbp+arg_8]
0x1400075e9  test    eax, eax
0x1400075eb  js      short loc_1400075F2
0x1400075ed  test    r14b, r14b
0x1400075f0  jnz     short loc_140007602
0x1400075f2  mov     rcx, r12
0x1400075f5  call    SmCheckProcessOrigin
0x1400075fa  mov     r15, rax
0x1400075fd  test    r14b, r14b
0x140007600  jz      short loc_140007607
0x140007602  test    rsi, rsi
0x140007605  jnz     short loc_140007616
0x140007607  test    r15, r15
0x14000760a  jnz     short loc_140007611
0x14000760c  test    rdi, rdi
0x14000760f  jz      short loc_14000767F
0x140007611  test    rsi, rsi
0x140007614  jz      short loc_140007623
0x140007616  mov     rax, [rsi+8]
0x14000761a  mov     rcx, [rax+20h]
0x14000761e  mov     r14, [rcx]
0x140007621  jmp     short loc_140007638
0x140007623  test    r15, r15
0x140007626  jz      short loc_14000762E
0x140007628  mov     r14, [r15+20h]
0x14000762c  jmp     short loc_140007638
0x14000762e  test    rdi, rdi
0x140007631  mov     r14, r13
0x140007634  cmovnz  r14, rdi
0x140007638  mov     eax, [r14+8]
0x14000763c  test    eax, 0FFFFFFFCh
0x140007641  jnz     short loc_140007677
0x140007643  cmp     eax, 2
0x140007646  jz      short loc_140007677
0x140007648  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x14000764c  mov     rcx, r12; Process
0x14000764f  call    cs:__imp_SeLocateProcessImageName
0x140007656  nop     dword ptr [rax+rax+00h]
0x14000765b  lea     r8, qword_140003130
0x140007662  mov     rcx, r14
0x140007665  test    eax, eax
0x140007667  lea     rdx, [rbp+var_18]
0x14000766b  mov     ebx, eax
0x14000766d  cmovns  r8, [rbp+pImageFileName]
0x140007672  call    SmRegisterUninstallStringWithSessionOrigin
0x140007677  mov     rcx, r15
0x14000767a  call    SmReleaseOriginProcessData
0x14000767f  test    rsi, rsi
0x140007682  jz      short loc_140007698
0x140007684  mov     edx, 41746D73h; Tag
0x140007689  mov     rcx, rsi; P
0x14000768c  call    cs:__imp_ExFreePoolWithTag
0x140007693  nop     dword ptr [rax+rax+00h]
0x140007698  test    rdi, rdi
0x14000769b  jz      short loc_1400076B6
0x14000769d  mov     edx, 53746D73h; Tag
0x1400076a2  mov     rcx, rdi; P
0x1400076a5  call    cs:__imp_ExFreePoolWithTag
0x1400076ac  nop     dword ptr [rax+rax+00h]
0x1400076b1  jmp     short loc_1400076B6
0x1400076b3  mov     ebx, r13d
0x1400076b6  mov     rcx, [rbp+pImageFileName]; P
0x1400076ba  test    rcx, rcx
0x1400076bd  jz      short loc_1400076CD
0x1400076bf  xor     edx, edx; Tag
0x1400076c1  call    cs:__imp_ExFreePoolWithTag
0x1400076c8  nop     dword ptr [rax+rax+00h]
0x1400076cd  mov     eax, ebx
0x1400076cf  mov     rbx, [rsp+60h+arg_0]
0x1400076d7  add     rsp, 60h
0x1400076db  pop     r15
0x1400076dd  pop     r14
0x1400076df  pop     r13
0x1400076e1  pop     r12
0x1400076e3  pop     rdi
0x1400076e4  pop     rsi
0x1400076e5  pop     rbp
0x1400076e6  retn
```
