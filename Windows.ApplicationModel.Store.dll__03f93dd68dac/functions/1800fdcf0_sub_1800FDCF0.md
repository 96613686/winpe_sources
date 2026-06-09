# sub_1800FDCF0

- ea: `0x1800fdcf0`
- end: `0x1800fdeba`
- name: `sub_1800FDCF0`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180016250`
- `0x18001b7b4`
- `0x18003c3ac`
- `0x1800dd3d4`
- `0x1800dfbdc`
- `0x1800fdcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fdd8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fdd8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fde4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fde4b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800fdd29`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800fdd29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fdddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fde99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fdd3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fdd52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fdd3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800fdd52`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_1800FDCF0(__int64 a1, HSTRING a2, HSTRING a3, _BYTE *a4)
{
  HRESULT v8; // edi
  HSTRING v9; // rbx
  _DWORD *v10; // r14
  __int64 v11; // r15
  HSTRING newString[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+98h] [rbp+58h] BYREF

  *a4 = 0;
  if ( !*(_BYTE *)(a1 + 152) )
    RoOriginateError(2147549183LL, 0);
  newString[0] = 0;
  v8 = WindowsDuplicateString(a2, newString);
  if ( v8 >= 0 )
  {
    v8 = WindowsDuplicateString(a3, &string);
    v9 = 0;
    if ( v8 < 0 )
    {
      string = 0;
      goto LABEL_21;
    }
    v10 = (_DWORD *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !*v10 )
        *v10 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    sub_180016250(&v14, *(unsigned __int8 *)(a1 + 154), a1 + 156);
    sub_18001B7B4(a1 + 144);
    v14 = 0;
    v8 = sub_1800DD3D4(a1 + 40, newString, &v14);
    if ( v8 >= 0 )
    {
      v11 = v14;
      if ( v14 )
      {
        v9 = *(HSTRING *)(v14 + 8);
        WindowsDeleteString(0);
        *(_QWORD *)(v11 + 8) = string;
        *a4 = 1;
LABEL_17:
        string = 0;
        goto LABEL_18;
      }
      if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
      {
        v8 = -2147024882;
        goto LABEL_18;
      }
      v14 = 0;
      v8 = sub_1800DFBDC(a1 + 40, newString, &string, &v14);
      v9 = 0;
      if ( v8 >= 0 )
      {
        newString[0] = 0;
        goto LABEL_17;
      }
    }
LABEL_18:
    if ( *(_DWORD *)(a1 + 128) == 1 )
      *v10 += 0x10000000;
    else
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 136));
LABEL_21:
    WindowsDeleteString(v9);
    WindowsDeleteString(string);
    if ( v8 >= 0 )
      v8 = sub_18003C3AC((unsigned __int8)v14, *(unsigned __int8 *)(a1 + 153), a1, *a4 != 0 ? 3 : 1, a2);
  }
  WindowsDeleteString(newString[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800fdcf0  mov     [rsp-38h+arg_8], rbx
0x1800fdcf5  push    rbp
0x1800fdcf6  push    rsi
0x1800fdcf7  push    rdi
0x1800fdcf8  push    r12
0x1800fdcfa  push    r13
0x1800fdcfc  push    r14
0x1800fdcfe  push    r15
0x1800fdd00  mov     rbp, rsp
0x1800fdd03  sub     rsp, 40h
0x1800fdd07  mov     r12, r9
0x1800fdd0a  mov     rbx, r8
0x1800fdd0d  mov     r13, rdx
0x1800fdd10  mov     rsi, rcx
0x1800fdd13  xor     r15d, r15d
0x1800fdd16  mov     [r9], r15b
0x1800fdd19  cmp     [rcx+98h], r15b
0x1800fdd20  jnz     short loc_1800FDD30
0x1800fdd22  xor     edx, edx
0x1800fdd24  mov     ecx, 8000FFFFh
0x1800fdd29  call    cs:RoOriginateError
0x1800fdd2f  nop
0x1800fdd30  mov     [rbp+newString], r15
0x1800fdd34  lea     rdx, [rbp+newString]; newString
0x1800fdd38  mov     rcx, r13; string
0x1800fdd3b  call    cs:WindowsDuplicateString
0x1800fdd41  mov     edi, eax
0x1800fdd43  test    eax, eax
0x1800fdd45  js      loc_1800FDE95
0x1800fdd4b  lea     rdx, [rbp+string]; newString
0x1800fdd4f  mov     rcx, rbx; string
0x1800fdd52  call    cs:WindowsDuplicateString
0x1800fdd58  mov     edi, eax
0x1800fdd5a  mov     rbx, r15
0x1800fdd5d  test    eax, eax
0x1800fdd5f  jns     short loc_1800FDD6A
0x1800fdd61  mov     [rbp+string], r15
0x1800fdd65  jmp     loc_1800FDE52
0x1800fdd6a  lea     r14, [rsi+88h]
0x1800fdd71  cmp     dword ptr [rsi+80h], 1
0x1800fdd78  jnz     short loc_1800FDD88
0x1800fdd7a  cmp     [r14], r15d
0x1800fdd7d  jnz     short loc_1800FDD92
0x1800fdd7f  mov     dword ptr [r14], 0F0000000h
0x1800fdd86  jmp     short loc_1800FDD92
0x1800fdd88  mov     rcx, r14; SRWLock
0x1800fdd8b  call    cs:AcquireSRWLockExclusive
0x1800fdd91  nop
0x1800fdd92  lea     r8, [rsi+9Ch]
0x1800fdd99  movzx   edx, byte ptr [rsi+9Ah]
0x1800fdda0  lea     rcx, [rbp+arg_0]
0x1800fdda4  call    sub_180016250
0x1800fdda9  lea     rcx, [rsi+90h]
0x1800fddb0  call    sub_18001B7B4
0x1800fddb5  mov     [rbp+arg_0], r15
0x1800fddb9  lea     rcx, [rsi+28h]
0x1800fddbd  lea     r8, [rbp+arg_0]
0x1800fddc1  lea     rdx, [rbp+newString]
0x1800fddc5  call    sub_1800DD3D4
0x1800fddca  mov     edi, eax
0x1800fddcc  test    eax, eax
0x1800fddce  js      short loc_1800FDE36
0x1800fddd0  mov     r15, [rbp+arg_0]
0x1800fddd4  test    r15, r15
0x1800fddd7  jz      short loc_1800FDDF8
0x1800fddd9  mov     rbx, [r15+8]
0x1800fdddd  xor     ecx, ecx; string
0x1800fdddf  call    cs:WindowsDeleteString
0x1800fdde5  nop
0x1800fdde6  mov     rax, [rbp+string]
0x1800fddea  mov     [r15+8], rax
0x1800fddee  xor     r15d, r15d
0x1800fddf1  mov     byte ptr [r12], 1
0x1800fddf6  jmp     short loc_1800FDE32
0x1800fddf8  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x1800fde00  jnz     short loc_1800FDE09
0x1800fde02  mov     edi, 8007000Eh
0x1800fde07  jmp     short loc_1800FDE36
0x1800fde09  xor     r15d, r15d
0x1800fde0c  mov     [rbp+arg_0], r15
0x1800fde10  lea     r9, [rbp+arg_0]
0x1800fde14  lea     r8, [rbp+string]
0x1800fde18  lea     rdx, [rbp+newString]
0x1800fde1c  lea     rcx, [rsi+28h]
0x1800fde20  call    sub_1800DFBDC
0x1800fde25  mov     edi, eax
0x1800fde27  mov     ebx, r15d
0x1800fde2a  test    eax, eax
0x1800fde2c  js      short loc_1800FDE36
0x1800fde2e  mov     [rbp+newString], r15
0x1800fde32  mov     [rbp+string], r15
0x1800fde36  cmp     dword ptr [rsi+80h], 1
0x1800fde3d  jnz     short loc_1800FDE48
0x1800fde3f  add     dword ptr [r14], 10000000h
0x1800fde46  jmp     short loc_1800FDE52
0x1800fde48  mov     rcx, r14; SRWLock
0x1800fde4b  call    cs:ReleaseSRWLockExclusive
0x1800fde51  nop
0x1800fde52  mov     rcx, rbx; string
0x1800fde55  call    cs:WindowsDeleteString
0x1800fde5b  nop
0x1800fde5c  mov     rcx, [rbp+string]; string
0x1800fde60  call    cs:WindowsDeleteString
0x1800fde66  nop
0x1800fde67  test    edi, edi
0x1800fde69  js      short loc_1800FDE95
0x1800fde6b  mov     al, [r12]
0x1800fde6f  neg     al
0x1800fde71  sbb     r9d, r9d
0x1800fde74  and     r9d, 2
0x1800fde78  inc     r9d
0x1800fde7b  mov     [rsp+40h+var_20], r13
0x1800fde80  mov     r8, rsi
0x1800fde83  movzx   edx, byte ptr [rsi+99h]
0x1800fde8a  movzx   ecx, byte ptr [rbp+arg_0]
0x1800fde8e  call    sub_18003C3AC
0x1800fde93  mov     edi, eax
0x1800fde95  mov     rcx, [rbp+newString]; string
0x1800fde99  call    cs:WindowsDeleteString
0x1800fde9f  nop
0x1800fdea0  mov     eax, edi
0x1800fdea2  mov     rbx, [rsp+40h+arg_8]
0x1800fdeaa  add     rsp, 40h
0x1800fdeae  pop     r15
0x1800fdeb0  pop     r14
0x1800fdeb2  pop     r13
0x1800fdeb4  pop     r12
0x1800fdeb6  pop     rdi
0x1800fdeb7  pop     rsi
0x1800fdeb8  pop     rbp
0x1800fdeb9  retn
```
