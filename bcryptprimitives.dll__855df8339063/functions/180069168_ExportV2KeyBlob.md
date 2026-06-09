# ExportV2KeyBlob

- ea: `0x180069168`
- end: `0x1800693a5`
- name: `ExportV2KeyBlob`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800697b0`

## callees

- `0x18000ecb0`
- `0x1800497f0`
- `0x1800525dc`
- `0x180056cf0`
- `0x180069168`
- `0x18007186c`
- `0x18007f765`

## string_xrefs

- `0x180069376`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ExportV2KeyBlob(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  int v5; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // r14d
  int v15; // ebp
  __int64 v16; // r15
  __int64 v17; // r12
  unsigned int Value; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v22; // [rsp+40h] [rbp-48h]
  __int64 v23; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 16);
  LODWORD(v23) = 0;
  v10 = 3 * *(_DWORD *)(a1 + 12) + 2 * (v5 + 14);
  if ( !wcscmp_0(a2, L"DSAPRIVATEBLOB") || !wcscmp_0(a2, L"PRIVATEBLOB") )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 40) + 4LL) )
    {
      v11 = -1073741811;
      v12 = 2279;
      v13 = 3221225485LL;
LABEL_21:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v12);
      return v11;
    }
    v10 += v5;
  }
  v11 = 0;
  *a5 = v10;
  if ( a3 )
  {
    if ( a4 >= v10 )
    {
      a3[1] = *(_DWORD *)(a1 + 12);
      a3[5] = *(_DWORD *)(a1 + 16);
      a3[4] = *(_DWORD *)(a1 + 16);
      a3[3] = *(_DWORD *)(a1 + 20);
      a3[2] = *(_DWORD *)(a1 + 24);
      if ( !wcscmp_0(a2, L"DSAPUBLICBLOB") || !wcscmp_0(a2, L"PUBLICBLOB") )
      {
        v15 = 0;
        *a3 = 843206724;
        v14 = 0;
      }
      else
      {
        if ( wcscmp_0(a2, L"DSAPRIVATEBLOB") && wcscmp_0(a2, L"PRIVATEBLOB") )
        {
          v11 = -1073741637;
          v12 = 2340;
          v13 = 3221225659LL;
          goto LABEL_21;
        }
        *a3 = 844517444;
        v14 = *(_DWORD *)(a1 + 16);
        v15 = 3 * *(_DWORD *)(a1 + 12) + 28 + (_DWORD)a3 + 2 * v14;
      }
      v16 = *(unsigned int *)(a1 + 16);
      v17 = *(unsigned int *)(a1 + 12);
      Value = SymCryptDlgroupGetValue(
                *(_QWORD *)(a1 + 32),
                (int)v16 + (int)a3 + 28 + (int)v16,
                *(_DWORD *)(a1 + 12),
                (int)v16 + (int)a3 + 28,
                v16,
                (__int64)a3 + v16 + v16 + v17 + 28,
                v17,
                2,
                v22,
                a3 + 7,
                v16,
                (__int64)&v23);
      if ( Value )
      {
        v19 = SymcryptErrorCodeToNtStatus(Value);
        v12 = 2369;
      }
      else
      {
        ReverseMemCopy(a3 + 6, &v23, 4);
        v20 = SymCryptDlkeyGetValue(
                *(_QWORD *)(a1 + 40),
                v15,
                v14,
                2 * (int)v17 + 28 + (int)a3 + 2 * (int)v16,
                *(unsigned int *)(a1 + 12));
        if ( !v20 )
          return v11;
        v19 = SymcryptErrorCodeToNtStatus(v20);
        v12 = 2386;
      }
      v13 = v19;
      v11 = v19;
      goto LABEL_21;
    }
    return (unsigned int)-1073741789;
  }
  return v11;
}

```

## disassembly

```asm
0x180069168  mov     rax, rsp
0x18006916b  mov     [rax+10h], rbx
0x18006916f  mov     [rax+18h], rbp
0x180069173  push    rsi
0x180069174  push    rdi
0x180069175  push    r12
0x180069177  push    r14
0x180069179  push    r15
0x18006917b  sub     rsp, 60h
0x18006917f  mov     ebx, [rcx+10h]
0x180069182  mov     rbp, rdx
0x180069185  mov     dword ptr [rax+8], 0
0x18006918c  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x180069193  mov     eax, [rcx+0Ch]
0x180069196  mov     rdi, rcx
0x180069199  mov     rcx, rbp; String1
0x18006919c  mov     r15d, r9d
0x18006919f  lea     r14d, [rbx+0Eh]
0x1800691a3  mov     rsi, r8
0x1800691a6  lea     r10d, [rax+rax*2]
0x1800691aa  lea     r14d, [r10+r14*2]
0x1800691ae  call    wcscmp_0
0x1800691b3  test    eax, eax
0x1800691b5  jz      short loc_1800691CA
0x1800691b7  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x1800691be  mov     rcx, rbp; String1
0x1800691c1  call    wcscmp_0
0x1800691c6  test    eax, eax
0x1800691c8  jnz     short loc_1800691EC
0x1800691ca  mov     rax, [rdi+28h]
0x1800691ce  cmp     byte ptr [rax+4], 0
0x1800691d2  jnz     short loc_1800691E9
0x1800691d4  mov     ebx, 0C000000Dh
0x1800691d9  mov     r9d, 8E7h
0x1800691df  mov     ecx, 0C000000Dh
0x1800691e4  jmp     loc_180069376
0x1800691e9  add     r14d, ebx
0x1800691ec  mov     rax, [rsp+88h+arg_20]
0x1800691f4  xor     ebx, ebx
0x1800691f6  mov     [rax], r14d
0x1800691f9  test    rsi, rsi
0x1800691fc  jz      loc_180069389
0x180069202  cmp     r15d, r14d
0x180069205  jnb     short loc_180069211
0x180069207  mov     ebx, 0C0000023h
0x18006920c  jmp     loc_180069389
0x180069211  mov     eax, [rdi+0Ch]
0x180069214  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x18006921b  mov     [rsi+4], eax
0x18006921e  mov     rcx, rbp; String1
0x180069221  mov     eax, [rdi+10h]
0x180069224  mov     [rsi+14h], eax
0x180069227  mov     eax, [rdi+10h]
0x18006922a  mov     [rsi+10h], eax
0x18006922d  mov     eax, [rdi+14h]
0x180069230  mov     [rsi+0Ch], eax
0x180069233  mov     eax, [rdi+18h]
0x180069236  mov     [rsi+8], eax
0x180069239  call    wcscmp_0
0x18006923e  test    eax, eax
0x180069240  jz      short loc_1800692B0
0x180069242  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180069249  mov     rcx, rbp; String1
0x18006924c  call    wcscmp_0
0x180069251  test    eax, eax
0x180069253  jz      short loc_1800692B0
0x180069255  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18006925c  mov     rcx, rbp; String1
0x18006925f  call    wcscmp_0
0x180069264  test    eax, eax
0x180069266  jz      short loc_180069290
0x180069268  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18006926f  mov     rcx, rbp; String1
0x180069272  call    wcscmp_0
0x180069277  test    eax, eax
0x180069279  jz      short loc_180069290
0x18006927b  mov     ebx, 0C00000BBh
0x180069280  mov     r9d, 924h
0x180069286  mov     ecx, 0C00000BBh
0x18006928b  jmp     loc_180069376
0x180069290  mov     dword ptr [rsi], 32565044h
0x180069296  mov     r14d, [rdi+10h]
0x18006929a  mov     eax, [rdi+0Ch]
0x18006929d  lea     ebp, [r14+r14]
0x1800692a1  lea     edx, [rax+rax*2]
0x1800692a4  add     rbp, rsi
0x1800692a7  add     rdx, 1Ch
0x1800692ab  add     rbp, rdx
0x1800692ae  jmp     short loc_1800692BB
0x1800692b0  xor     ebp, ebp
0x1800692b2  mov     dword ptr [rsi], 32425044h
0x1800692b8  xor     r14d, r14d
0x1800692bb  mov     r15d, [rdi+10h]
0x1800692bf  lea     rcx, [rsi+1Ch]
0x1800692c3  mov     r12d, [rdi+0Ch]
0x1800692c7  lea     r8, [rsp+88h+arg_0]
0x1800692cf  mov     [rsp+88h+var_30], r8; __int64
0x1800692d4  mov     r8d, r12d; int
0x1800692d7  mov     [rsp+88h+var_38], r15; __int64
0x1800692dc  mov     [rsp+88h+var_40], rcx; void *
0x1800692e1  lea     r9, [r15+rcx]; int
0x1800692e5  mov     rcx, [rdi+20h]; int
0x1800692e9  lea     rdx, [r9+r15]; int
0x1800692ed  mov     [rsp+88h+var_50], 2; int
0x1800692f5  lea     rax, [r12+rdx]
0x1800692f9  mov     [rsp+88h+var_58], r12; __int64
0x1800692fe  mov     [rsp+88h+var_60], rax; __int64
0x180069303  mov     [rsp+88h+var_68], r15; __int64
0x180069308  call    SymCryptDlgroupGetValue
0x18006930d  test    eax, eax
0x18006930f  jz      short loc_180069320
0x180069311  mov     ecx, eax
0x180069313  call    SymcryptErrorCodeToNtStatus
0x180069318  mov     r9d, 941h
0x18006931e  jmp     short loc_180069372
0x180069320  lea     rcx, [rsi+18h]
0x180069324  mov     r8d, 4
0x18006932a  lea     rdx, [rsp+88h+arg_0]
0x180069332  call    ReverseMemCopy
0x180069337  mov     r10d, [rdi+0Ch]
0x18006933b  lea     r9d, [r15+r15]
0x18006933f  add     r9, rsi
0x180069342  mov     r8d, r14d
0x180069345  lea     ecx, [r12+r12]
0x180069349  mov     [rsp+88h+var_68], r10
0x18006934e  add     rcx, 1Ch
0x180069352  mov     rdx, rbp
0x180069355  add     r9, rcx
0x180069358  mov     rcx, [rdi+28h]
0x18006935c  call    SymCryptDlkeyGetValue
0x180069361  test    eax, eax
0x180069363  jz      short loc_180069389
0x180069365  mov     ecx, eax
0x180069367  call    SymcryptErrorCodeToNtStatus
0x18006936c  mov     r9d, 952h
0x180069372  mov     ecx, eax
0x180069374  mov     ebx, eax
0x180069376  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006937d  lea     rdx, aStatus; "Status"
0x180069384  call    DebugTraceError
0x180069389  lea     r11, [rsp+88h+var_28]
0x18006938e  mov     eax, ebx
0x180069390  mov     rbx, [r11+38h]
0x180069394  mov     rbp, [r11+40h]
0x180069398  mov     rsp, r11
0x18006939b  pop     r15
0x18006939d  pop     r14
0x18006939f  pop     r12
0x1800693a1  pop     rdi
0x1800693a2  pop     rsi
0x1800693a3  retn
```
