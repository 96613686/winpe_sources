# ValidateDSAKeyBlobV2Format

- ea: `0x180058834`
- end: `0x1800589fe`
- name: `ValidateDSAKeyBlobV2Format`
- size: `458`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800693c8`

## callees

- `0x18000ecb0`
- `0x180058834`
- `0x18007f765`

## string_xrefs

- `0x1800589cb`: `onecore\ds\security\cryptoapi\ncrypt\common\keyblobvalidate.c`

## pseudocode

```c
__int64 __fastcall ValidateDSAKeyBlobV2Format(_DWORD *a1, unsigned int a2, const wchar_t *a3, int *a4)
{
  int v4; // r15d
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r9d
  unsigned int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // ebx

  v4 = 0;
  if ( !a1 || !a3 )
  {
    v9 = 213;
    goto LABEL_36;
  }
  if ( a2 < 0x1C )
  {
    v9 = 220;
LABEL_36:
    v17 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\keyblobvalidate.c", v9);
    goto LABEL_37;
  }
  v10 = (unsigned int)a1[1];
  if ( (v10 & 7) != 0 || (unsigned int)(v10 - 129) > 0xFF )
  {
    v9 = 234;
    goto LABEL_36;
  }
  v11 = a1[5];
  v12 = a1[4];
  if ( v11 != v12 || v11 != 32 || a1[2] != 1 || a1[3] != (unsigned int)v10 > 0x80 )
  {
    v9 = 245;
    goto LABEL_36;
  }
  v13 = 3 * v10;
  if ( (unsigned __int64)(3 * v10) > 0xFFFFFFFF )
  {
    v9 = 253;
    goto LABEL_36;
  }
  v14 = v13 + 32;
  if ( v13 + 32 < v13 )
  {
    v9 = 261;
    goto LABEL_36;
  }
  v15 = v14 + v12;
  if ( v14 + v12 < v14 )
  {
    v9 = 269;
    goto LABEL_36;
  }
  v16 = v15 + 28;
  if ( v15 + 28 < v15 )
  {
    v9 = 277;
    goto LABEL_36;
  }
  if ( v15 + 60 < v15 + 28 )
  {
    v9 = 285;
    goto LABEL_36;
  }
  if ( !wcscmp_0(a3, L"DSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
  {
    if ( *a1 != 843206724 || a2 != v16 )
    {
      v9 = 296;
      goto LABEL_36;
    }
  }
  else
  {
    if ( wcscmp_0(a3, L"DSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
    {
      v9 = 315;
      goto LABEL_36;
    }
    v4 = 1;
    if ( *a1 != 844517444 || a2 != v16 + 32 )
    {
      v9 = 308;
      goto LABEL_36;
    }
  }
  v17 = 0;
LABEL_37:
  *a4 = v4;
  return v17;
}

```

## disassembly

```asm
0x180058834  push    rbx
0x180058836  push    rbp
0x180058837  push    rsi
0x180058838  push    rdi
0x180058839  push    r12
0x18005883b  push    r14
0x18005883d  push    r15
0x18005883f  sub     rsp, 20h
0x180058843  xor     r15d, r15d
0x180058846  mov     r12, r9
0x180058849  mov     rsi, r8
0x18005884c  mov     ebp, edx
0x18005884e  mov     rbx, rcx
0x180058851  test    rcx, rcx
0x180058854  jz      loc_1800589C5
0x18005885a  test    r8, r8
0x18005885d  jz      loc_1800589C5
0x180058863  cmp     edx, 1Ch
0x180058866  jnb     short loc_180058873
0x180058868  mov     r9d, 0DCh
0x18005886e  jmp     loc_1800589CB
0x180058873  mov     ecx, [rcx+4]
0x180058876  test    cl, 7
0x180058879  jnz     loc_1800589BD
0x18005887f  lea     eax, [rcx-81h]
0x180058885  cmp     eax, 0FFh
0x18005888a  ja      loc_1800589BD
0x180058890  mov     edx, [rbx+14h]
0x180058893  mov     r9d, [rbx+10h]
0x180058897  cmp     edx, r9d
0x18005889a  jnz     loc_1800589B5
0x1800588a0  cmp     edx, 20h ; ' '
0x1800588a3  jnz     loc_1800589B5
0x1800588a9  cmp     dword ptr [rbx+8], 1
0x1800588ad  jnz     loc_1800589B5
0x1800588b3  xor     eax, eax
0x1800588b5  cmp     ecx, 80h
0x1800588bb  setnbe  al
0x1800588be  cmp     [rbx+0Ch], eax
0x1800588c1  jnz     loc_1800589B5
0x1800588c7  lea     r8, [rcx+rcx*2]
0x1800588cb  mov     eax, 0FFFFFFFFh
0x1800588d0  cmp     r8, rax
0x1800588d3  ja      loc_1800589AD
0x1800588d9  lea     ecx, [r8+rdx]
0x1800588dd  cmp     ecx, r8d
0x1800588e0  jnb     short loc_1800588ED
0x1800588e2  mov     r9d, 105h
0x1800588e8  jmp     loc_1800589CB
0x1800588ed  lea     eax, [rcx+r9]
0x1800588f1  cmp     eax, ecx
0x1800588f3  jnb     short loc_180058900
0x1800588f5  mov     r9d, 10Dh
0x1800588fb  jmp     loc_1800589CB
0x180058900  lea     edi, [rax+1Ch]
0x180058903  cmp     edi, eax
0x180058905  jnb     short loc_180058912
0x180058907  mov     r9d, 115h
0x18005890d  jmp     loc_1800589CB
0x180058912  lea     r14d, [rdi+rdx]
0x180058916  cmp     r14d, edi
0x180058919  jnb     short loc_180058926
0x18005891b  mov     r9d, 11Dh
0x180058921  jmp     loc_1800589CB
0x180058926  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x18005892d  mov     rcx, rsi; String1
0x180058930  call    wcscmp_0
0x180058935  test    eax, eax
0x180058937  jz      short loc_180058995
0x180058939  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180058940  mov     rcx, rsi; String1
0x180058943  call    wcscmp_0
0x180058948  test    eax, eax
0x18005894a  jz      short loc_180058995
0x18005894c  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x180058953  mov     rcx, rsi; String1
0x180058956  call    wcscmp_0
0x18005895b  test    eax, eax
0x18005895d  jz      short loc_18005897A
0x18005895f  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180058966  mov     rcx, rsi; String1
0x180058969  call    wcscmp_0
0x18005896e  test    eax, eax
0x180058970  jz      short loc_18005897A
0x180058972  mov     r9d, 13Bh
0x180058978  jmp     short loc_1800589CB
0x18005897a  cmp     dword ptr [rbx], 32565044h
0x180058980  mov     r15d, 1
0x180058986  jnz     short loc_18005898D
0x180058988  cmp     ebp, r14d
0x18005898b  jz      short loc_1800589A1
0x18005898d  mov     r9d, 134h
0x180058993  jmp     short loc_1800589CB
0x180058995  cmp     dword ptr [rbx], 32425044h
0x18005899b  jnz     short loc_1800589A5
0x18005899d  cmp     ebp, edi
0x18005899f  jnz     short loc_1800589A5
0x1800589a1  xor     ebx, ebx
0x1800589a3  jmp     short loc_1800589E8
0x1800589a5  mov     r9d, 128h
0x1800589ab  jmp     short loc_1800589CB
0x1800589ad  mov     r9d, 0FDh
0x1800589b3  jmp     short loc_1800589CB
0x1800589b5  mov     r9d, 0F5h
0x1800589bb  jmp     short loc_1800589CB
0x1800589bd  mov     r9d, 0EAh
0x1800589c3  jmp     short loc_1800589CB
0x1800589c5  mov     r9d, 0D5h
0x1800589cb  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800589d2  mov     ecx, 0C000000Dh
0x1800589d7  lea     rdx, aStatus; "Status"
0x1800589de  mov     ebx, 0C000000Dh
0x1800589e3  call    DebugTraceError
0x1800589e8  mov     [r12], r15d
0x1800589ec  mov     eax, ebx
0x1800589ee  add     rsp, 20h
0x1800589f2  pop     r15
0x1800589f4  pop     r14
0x1800589f6  pop     r12
0x1800589f8  pop     rdi
0x1800589f9  pop     rsi
0x1800589fa  pop     rbp
0x1800589fb  pop     rbx
0x1800589fc  retn
```
