# SuInitializeDriveTemplateList_FindPrimordials

- ea: `0x140015a98`
- end: `0x140015b54`
- name: `SuInitializeDriveTemplateList_FindPrimordials`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001593c`

## callees

- `0x140015a98`
- `0x140015bfc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140015b3b`
- `KERNEL32!SetLastError` at `0x140015b3b`
- `KERNEL32!GetLastError` at `0x140015af7`
- `KERNEL32!GetLastError` at `0x140015af7`

## pseudocode

```c
__int64 __fastcall SuInitializeDriveTemplateList_FindPrimordials(int a1, int *a2, __int64 a3, DWORD *a4, _DWORD *a5)
{
  int v8; // ebp
  unsigned int v9; // ebx
  DWORD v10; // edi
  int i; // r14d
  __int64 v12; // rax
  int Primordial; // r15d
  DWORD LastError; // eax

  v8 = a1;
  v9 = a1 == 0;
  v10 = 0;
  for ( i = 0; v8; --v8 )
  {
    v12 = *(_QWORD *)(a3 + 24) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v12 )
      v12 = *(_QWORD *)(a3 + 32) - *(_QWORD *)GUID_NULL.Data4;
    Primordial = SuInitializeDriveTemplate_FindPrimordial(*a2, v12 == 0, (_DWORD *)a3);
    if ( Primordial )
      LastError = 0;
    else
      LastError = GetLastError();
    *a4 = LastError;
    v9 |= Primordial;
    if ( v10 )
      LastError = v10;
    v10 = LastError;
    ++a2;
    i |= Primordial == 0;
    a3 += 3120;
    ++a4;
  }
  *a5 = i;
  SetLastError(v10);
  return v9;
}

```

## disassembly

```asm
0x140015a98  push    rbx
0x140015a9a  push    rbp
0x140015a9b  push    rsi
0x140015a9c  push    rdi
0x140015a9d  push    r12
0x140015a9f  push    r13
0x140015aa1  push    r14
0x140015aa3  push    r15
0x140015aa5  sub     rsp, 28h
0x140015aa9  xor     ebx, ebx
0x140015aab  mov     r13, r9
0x140015aae  test    ecx, ecx
0x140015ab0  mov     rsi, r8
0x140015ab3  mov     r12, rdx
0x140015ab6  mov     ebp, ecx
0x140015ab8  setz    bl
0x140015abb  xor     edi, edi
0x140015abd  xor     r14d, r14d
0x140015ac0  test    ecx, ecx
0x140015ac2  jz      short loc_140015B2E
0x140015ac4  mov     rax, [rsi+18h]
0x140015ac8  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140015acf  jnz     short loc_140015ADC
0x140015ad1  mov     rax, [rsi+20h]
0x140015ad5  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140015adc  mov     ecx, [r12]
0x140015ae0  xor     edx, edx
0x140015ae2  test    rax, rax
0x140015ae5  mov     r8, rsi
0x140015ae8  setz    dl
0x140015aeb  call    SuInitializeDriveTemplate_FindPrimordial
0x140015af0  mov     r15d, eax
0x140015af3  test    eax, eax
0x140015af5  jnz     short loc_140015AFF
0x140015af7  call    cs:__imp_GetLastError
0x140015afd  jmp     short loc_140015B01
0x140015aff  xor     eax, eax
0x140015b01  mov     [r13+0], eax
0x140015b05  or      ebx, r15d
0x140015b08  test    edi, edi
0x140015b0a  cmovnz  eax, edi
0x140015b0d  mov     edi, eax
0x140015b0f  xor     eax, eax
0x140015b11  test    r15d, r15d
0x140015b14  setz    al
0x140015b17  add     r12, 4
0x140015b1b  or      r14d, eax
0x140015b1e  add     rsi, 0C30h
0x140015b25  add     r13, 4
0x140015b29  add     ebp, 0FFFFFFFFh
0x140015b2c  jnz     short loc_140015AC4
0x140015b2e  mov     rdx, [rsp+68h+arg_20]
0x140015b36  mov     ecx, edi; dwErrCode
0x140015b38  mov     [rdx], r14d
0x140015b3b  call    cs:__imp_SetLastError
0x140015b41  mov     eax, ebx
0x140015b43  add     rsp, 28h
0x140015b47  pop     r15
0x140015b49  pop     r14
0x140015b4b  pop     r13
0x140015b4d  pop     r12
0x140015b4f  pop     rdi
0x140015b50  pop     rsi
0x140015b51  pop     rbp
0x140015b52  pop     rbx
0x140015b53  retn
```
