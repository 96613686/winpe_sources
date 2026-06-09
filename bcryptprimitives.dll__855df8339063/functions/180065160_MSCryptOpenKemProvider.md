# MSCryptOpenKemProvider

- ea: `0x180065160`
- end: `0x18006524d`
- name: `MSCryptOpenKemProvider`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800102a0`
- `0x180065160`
- `0x18007f765`

## string_xrefs

- `0x1800651c7`: `Composite-ML-KEM`
- `0x18006522e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenKemProvider(_QWORD *a1, const wchar_t *a2, int a3)
{
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // edi
  _DWORD *v9; // rax

  if ( !a1 )
  {
    v5 = 756;
LABEL_3:
    v6 = -1073741811;
    v7 = 3221225485LL;
LABEL_16:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v5);
    return v6;
  }
  if ( !a2 )
  {
    v5 = 763;
    goto LABEL_3;
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v5 = 770;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"ML-KEM") )
  {
    v8 = 458753;
  }
  else
  {
    if ( wcscmp_0(a2, L"Composite-ML-KEM") )
    {
      v6 = -1073741637;
      v7 = 3221225659LL;
      v5 = 785;
      goto LABEL_16;
    }
    v8 = 458754;
  }
  v9 = (_DWORD *)SafeAllocaAllocateFromHeap(12);
  if ( !v9 )
  {
    v6 = -1073741801;
    v7 = 3221225495LL;
    v5 = 794;
    goto LABEL_16;
  }
  *v9 = 12;
  v6 = 0;
  v9[1] = 1297302849;
  v9[2] = v8;
  *a1 = v9;
  return v6;
}

```

## disassembly

```asm
0x180065160  mov     [rsp+arg_0], rbx
0x180065165  mov     [rsp+arg_8], rsi
0x18006516a  push    rdi
0x18006516b  sub     rsp, 20h
0x18006516f  mov     rbx, rdx
0x180065172  mov     rsi, rcx
0x180065175  test    rcx, rcx
0x180065178  jnz     short loc_18006518F
0x18006517a  mov     r9d, 2F4h
0x180065180  mov     ebx, 0C000000Dh
0x180065185  mov     ecx, 0C000000Dh
0x18006518a  jmp     loc_180065227
0x18006518f  test    rbx, rbx
0x180065192  jnz     short loc_18006519C
0x180065194  mov     r9d, 2FBh
0x18006519a  jmp     short loc_180065180
0x18006519c  test    r8d, 0FFFFFFFEh
0x1800651a3  jz      short loc_1800651AD
0x1800651a5  mov     r9d, 302h
0x1800651ab  jmp     short loc_180065180
0x1800651ad  lea     rdx, aMlKem; "ML-KEM"
0x1800651b4  mov     rcx, rbx; String1
0x1800651b7  call    wcscmp_0
0x1800651bc  test    eax, eax
0x1800651be  jnz     short loc_1800651C7
0x1800651c0  mov     edi, 70001h
0x1800651c5  jmp     short loc_1800651DF
0x1800651c7  lea     rdx, aCompositeMlKem; "Composite-ML-KEM"
0x1800651ce  mov     rcx, rbx; String1
0x1800651d1  call    wcscmp_0
0x1800651d6  test    eax, eax
0x1800651d8  jnz     short loc_180065217
0x1800651da  mov     edi, 70002h
0x1800651df  mov     ecx, 0Ch
0x1800651e4  call    SafeAllocaAllocateFromHeap
0x1800651e9  test    rax, rax
0x1800651ec  jnz     short loc_180065200
0x1800651ee  mov     ebx, 0C0000017h
0x1800651f3  mov     ecx, 0C0000017h
0x1800651f8  mov     r9d, 31Ah
0x1800651fe  jmp     short loc_180065227
0x180065200  mov     dword ptr [rax], 0Ch
0x180065206  xor     ebx, ebx
0x180065208  mov     dword ptr [rax+4], 4D534541h
0x18006520f  mov     [rax+8], edi
0x180065212  mov     [rsi], rax
0x180065215  jmp     short loc_18006523A
0x180065217  mov     ebx, 0C00000BBh
0x18006521c  mov     ecx, 0C00000BBh
0x180065221  mov     r9d, 311h
0x180065227  lea     rdx, aStatus; "Status"
0x18006522e  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065235  call    DebugTraceError
0x18006523a  mov     rsi, [rsp+28h+arg_8]
0x18006523f  mov     eax, ebx
0x180065241  mov     rbx, [rsp+28h+arg_0]
0x180065246  add     rsp, 20h
0x18006524a  pop     rdi
0x18006524b  retn
```
