# SdbpGetSystemSdbFilePath

- ea: `0x140042fec`
- end: `0x140043106`
- name: `SdbpGetSystemSdbFilePath`
- size: `282`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14002644c`
- `0x14002cf68`
- `0x140042e28`
- `0x140042fc4`

## callees

- `0x140007ad0`
- `0x14003e364`
- `0x140042fec`

## string_xrefs

- `0x140043048`: `SdbpGetSystemSdbFilePath`
- `0x1400430bb`: `SdbpGetSystemSdbFilePath`
- `0x1400430e6`: `SdbpGetSystemSdbFilePath`
- `0x1400430ae`: `SdbFileDetails missing function pointer for path.`
- `0x1400430d7`: `GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetSystemSdbFilePath(_WORD *a1, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 a6)
{
  unsigned __int64 i; // rdx
  __int64 *v9; // rcx
  unsigned int v10; // ebx
  __int64 (__fastcall *v12)(_WORD *, __int64, __int64, __int64); // rax
  __int64 v13; // r8
  int v14; // eax

  *a1 = 0;
  if ( a3 && a3 < 13 )
  {
    for ( i = 1; ; ++i )
    {
      if ( i >= 0xD )
        goto LABEL_7;
      v9 = &qword_14000A000[4 * i];
      if ( *(_DWORD *)v9 == a3 )
        break;
    }
    if ( !v9 )
    {
LABEL_7:
      AslLogCallPrintf(1, "SdbpGetSystemSdbFilePath", 1373, "SdbFileDetails missing array item for SdbFileType: %d", a3);
      return (unsigned int)-1073741275;
    }
    v12 = (__int64 (__fastcall *)(_WORD *, __int64, __int64, __int64))v9[2];
    if ( v12 )
    {
      v13 = a5;
      if ( !a5 )
        v13 = v9[1];
      v14 = v12(a1, 260, v13, a6);
      v10 = v14;
      if ( v14 < 0 )
        AslLogCallPrintf(
          1,
          "SdbpGetSystemSdbFilePath",
          1397,
          "GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]",
          a3,
          0,
          v14);
      else
        return 0;
    }
    else
    {
      AslLogCallPrintf(1, "SdbpGetSystemSdbFilePath", 1387, "SdbFileDetails missing function pointer for path.");
      return (unsigned int)-1073741595;
    }
  }
  else
  {
    return (unsigned int)-1073741583;
  }
  return v10;
}

```

## disassembly

```asm
0x140042fec  mov     [rsp+arg_0], rbx
0x140042ff1  push    rdi
0x140042ff2  sub     rsp, 40h
0x140042ff6  xor     eax, eax
0x140042ff8  mov     edi, r8d
0x140042ffb  mov     [rcx], ax
0x140042ffe  mov     r10, rcx
0x140043001  test    r8d, r8d
0x140043004  jz      loc_14004309F
0x14004300a  cmp     r8d, 0Dh
0x14004300e  jge     loc_14004309F
0x140043014  lea     edx, [rax+1]
0x140043017  cmp     rdx, 0Dh
0x14004301b  jnb     short loc_140043037
0x14004301d  mov     rax, rdx
0x140043020  lea     rcx, qword_14000A000
0x140043027  shl     rax, 5
0x14004302b  add     rcx, rax
0x14004302e  cmp     [rcx], edi
0x140043030  jnz     short loc_1400430A6
0x140043032  test    rcx, rcx
0x140043035  jnz     short loc_14004306C
0x140043037  lea     r9, aSdbfiledetails; "SdbFileDetails missing array item for S"...
0x14004303e  mov     [rsp+48h+var_28], edi
0x140043042  mov     r8d, 55Dh
0x140043048  lea     rdx, aSdbpgetsystems_1; "SdbpGetSystemSdbFilePath"
0x14004304f  mov     ecx, 1
0x140043054  call    AslLogCallPrintf
0x140043059  mov     ebx, 0C0000225h
0x14004305e  mov     eax, ebx
0x140043060  mov     rbx, [rsp+48h+arg_0]
0x140043065  add     rsp, 40h
0x140043069  pop     rdi
0x14004306a  retn
0x14004306c  mov     rax, [rcx+10h]
0x140043070  test    rax, rax
0x140043073  jz      short loc_1400430AE
0x140043075  mov     r8, [rsp+48h+arg_20]
0x14004307a  test    r8, r8
0x14004307d  jnz     short loc_140043083
0x14004307f  mov     r8, [rcx+8]
0x140043083  mov     r9, [rsp+48h+arg_28]
0x140043088  mov     edx, 104h
0x14004308d  mov     rcx, r10
0x140043090  call    _guard_dispatch_icall
0x140043095  mov     ebx, eax
0x140043097  test    eax, eax
0x140043099  js      short loc_1400430D3
0x14004309b  xor     ebx, ebx
0x14004309d  jmp     short loc_14004305E
0x14004309f  mov     ebx, 0C00000F1h
0x1400430a4  jmp     short loc_14004305E
0x1400430a6  inc     rdx
0x1400430a9  jmp     loc_140043017
0x1400430ae  lea     r9, aSdbfiledetails_0; "SdbFileDetails missing function pointer"...
0x1400430b5  mov     r8d, 56Bh
0x1400430bb  lea     rdx, aSdbpgetsystems_1; "SdbpGetSystemSdbFilePath"
0x1400430c2  mov     ecx, 1
0x1400430c7  call    AslLogCallPrintf
0x1400430cc  mov     ebx, 0C00000E5h
0x1400430d1  jmp     short loc_14004305E
0x1400430d3  mov     [rsp+48h+var_18], eax
0x1400430d7  lea     r9, aGetpathfunctio; "GetPathFunction (for SdbFileType %d, Is"...
0x1400430de  mov     [rsp+48h+var_20], 0
0x1400430e6  lea     rdx, aSdbpgetsystems_1; "SdbpGetSystemSdbFilePath"
0x1400430ed  mov     r8d, 575h
0x1400430f3  mov     [rsp+48h+var_28], edi
0x1400430f7  mov     ecx, 1
0x1400430fc  call    AslLogCallPrintf
0x140043101  jmp     loc_14004305E
```
