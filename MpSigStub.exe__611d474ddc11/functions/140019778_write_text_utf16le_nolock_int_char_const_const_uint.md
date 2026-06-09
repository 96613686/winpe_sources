# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x140019778`
- end: `0x140019896`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140019bc8`

## callees

- `0x140019778`
- `0x14001bf00`
- `0x14001c870`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019863`
- `KERNEL32!GetLastError` at `0x140019863`
- `KERNEL32!WriteFile` at `0x140019847`
- `KERNEL32!WriteFile` at `0x140019847`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = a3;
  v7 = *(void **)(qword_1400D69C0[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      NumberOfBytesWritten = 0;
      v10 = 2 * ((v8 - Buffer) >> 1);
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x140019778  mov     [rsp+arg_0], rbx
0x14001977d  mov     [rsp+arg_10], rbp
0x140019782  push    rsi
0x140019783  push    rdi
0x140019784  push    r14
0x140019786  mov     eax, 1450h
0x14001978b  call    __alloca_probe
0x140019790  sub     rsp, rax
0x140019793  mov     rax, cs:__security_cookie
0x14001979a  xor     rax, rsp
0x14001979d  mov     [rsp+1468h+var_28], rax
0x1400197a5  movsxd  r10, edx
0x1400197a8  mov     rdi, rcx
0x1400197ab  mov     rax, r10
0x1400197ae  mov     ebp, r9d
0x1400197b1  sar     rax, 6
0x1400197b5  lea     rcx, qword_1400D69C0
0x1400197bc  and     r10d, 3Fh
0x1400197c0  add     rbp, r8
0x1400197c3  mov     rsi, r8
0x1400197c6  mov     rax, [rcx+rax*8]
0x1400197ca  lea     rdx, [r10+r10*8]
0x1400197ce  mov     r14, [rax+rdx*8+28h]
0x1400197d3  xor     eax, eax
0x1400197d5  mov     [rdi], rax
0x1400197d8  mov     [rdi+8], eax
0x1400197db  cmp     r8, rbp
0x1400197de  jnb     loc_14001986B
0x1400197e4  lea     rbx, [rsp+1468h+Buffer]
0x1400197e9  cmp     rsi, rbp
0x1400197ec  jnb     short loc_14001981F
0x1400197ee  movzx   eax, word ptr [rsi]
0x1400197f1  add     rsi, 2
0x1400197f5  cmp     ax, 0Ah
0x1400197f9  jnz     short loc_14001980B
0x1400197fb  add     dword ptr [rdi+8], 2
0x1400197ff  mov     ecx, 0Dh
0x140019804  mov     [rbx], cx
0x140019807  add     rbx, 2
0x14001980b  mov     [rbx], ax
0x14001980e  add     rbx, 2
0x140019812  lea     rax, [rsp+1468h+var_2A]
0x14001981a  cmp     rbx, rax
0x14001981d  jb      short loc_1400197E9
0x14001981f  and     [rsp+1468h+NumberOfBytesWritten], 0
0x140019824  lea     rax, [rsp+1468h+Buffer]
0x140019829  and     [rsp+1468h+var_1448], 0
0x14001982f  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140019834  sub     rbx, rax
0x140019837  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14001983c  sar     rbx, 1
0x14001983f  mov     rcx, r14; hFile
0x140019842  add     ebx, ebx
0x140019844  mov     r8d, ebx; nNumberOfBytesToWrite
0x140019847  call    cs:WriteFile
0x14001984d  test    eax, eax
0x14001984f  jz      short loc_140019863
0x140019851  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x140019855  add     [rdi+4], eax
0x140019858  cmp     eax, ebx
0x14001985a  jb      short loc_14001986B
0x14001985c  cmp     rsi, rbp
0x14001985f  jb      short loc_1400197E4
0x140019861  jmp     short loc_14001986B
0x140019863  call    cs:GetLastError
0x140019869  mov     [rdi], eax
0x14001986b  mov     rax, rdi
0x14001986e  mov     rcx, [rsp+1468h+var_28]
0x140019876  xor     rcx, rsp; StackCookie
0x140019879  call    __security_check_cookie
0x14001987e  lea     r11, [rsp+1468h+var_18]
0x140019886  mov     rbx, [r11+20h]
0x14001988a  mov     rbp, [r11+30h]
0x14001988e  mov     rsp, r11
0x140019891  pop     r14
0x140019893  pop     rdi
0x140019894  pop     rsi
0x140019895  retn
```
