# ExportV1KeyBlob

- ea: `0x180068f50`
- end: `0x18006915f`
- name: `ExportV1KeyBlob`
- size: `527`
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
- `0x180068f50`
- `0x18007186c`
- `0x18007f765`

## string_xrefs

- `0x180069130`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ExportV1KeyBlob(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v9; // ebp
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // ebp
  int v14; // esi
  __int64 v15; // r15
  unsigned int Value; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-48h]
  __int64 v21; // [rsp+90h] [rbp+8h] BYREF

  LODWORD(v21) = 0;
  v9 = *(_DWORD *)(a1 + 12) + 2 * (*(_DWORD *)(a1 + 12) + 26);
  if ( !wcscmp_0(a2, L"DSAPRIVATEBLOB") || !wcscmp_0(a2, L"PRIVATEBLOB") )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 40) + 4LL) )
    {
      v10 = -1073741811;
      v11 = 2138;
      v12 = 3221225485LL;
LABEL_21:
      DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v11);
      return v10;
    }
    v9 += 20;
  }
  v10 = 0;
  *a5 = v9;
  if ( a3 )
  {
    if ( a4 >= v9 )
    {
      a3[1] = *(_DWORD *)(a1 + 12);
      if ( !wcscmp_0(a2, L"DSAPUBLICBLOB") || !wcscmp_0(a2, L"PUBLICBLOB") )
      {
        v14 = 0;
        *a3 = 1112560452;
        v13 = 0;
      }
      else
      {
        if ( wcscmp_0(a2, L"DSAPRIVATEBLOB") && wcscmp_0(a2, L"PRIVATEBLOB") )
        {
          v10 = -1073741637;
          v11 = 2192;
          v12 = 3221225659LL;
          goto LABEL_21;
        }
        *a3 = 1448104772;
        v13 = 20;
        v14 = (_DWORD)a3 + 3 * *(_DWORD *)(a1 + 12) + 52;
      }
      v15 = *(unsigned int *)(a1 + 12);
      Value = SymCryptDlgroupGetValue(
                *(_QWORD *)(a1 + 32),
                (int)a3 + 52,
                *(_DWORD *)(a1 + 12),
                (int)a3 + 32,
                20,
                (__int64)a3 + v15 + 52,
                v15,
                2,
                v20,
                a3 + 3,
                20,
                (__int64)&v21);
      if ( Value )
      {
        v17 = SymcryptErrorCodeToNtStatus(Value);
        v11 = 2219;
      }
      else
      {
        ReverseMemCopy(a3 + 2, &v21, 4);
        v18 = SymCryptDlkeyGetValue(
                *(_QWORD *)(a1 + 40),
                v14,
                v13,
                (int)a3 + 2 * (int)v15 + 52,
                *(unsigned int *)(a1 + 12));
        if ( !v18 )
          return v10;
        v17 = SymcryptErrorCodeToNtStatus(v18);
        v11 = 2236;
      }
      v12 = v17;
      v10 = v17;
      goto LABEL_21;
    }
    return (unsigned int)-1073741789;
  }
  return v10;
}

```

## disassembly

```asm
0x180068f50  mov     rax, rsp
0x180068f53  mov     [rax+10h], rbx
0x180068f57  mov     [rax+18h], rbp
0x180068f5b  push    rsi
0x180068f5c  push    rdi
0x180068f5d  push    r12
0x180068f5f  push    r14
0x180068f61  push    r15
0x180068f63  sub     rsp, 60h
0x180068f67  mov     rsi, rdx
0x180068f6a  mov     dword ptr [rax+8], 0
0x180068f71  mov     eax, [rcx+0Ch]
0x180068f74  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x180068f7b  mov     r14, rcx
0x180068f7e  mov     r15d, r9d
0x180068f81  mov     rcx, rsi; String1
0x180068f84  mov     rdi, r8
0x180068f87  lea     ebp, [rax+1Ah]
0x180068f8a  lea     ebp, [rax+rbp*2]
0x180068f8d  call    wcscmp_0
0x180068f92  test    eax, eax
0x180068f94  jz      short loc_180068FA9
0x180068f96  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180068f9d  mov     rcx, rsi; String1
0x180068fa0  call    wcscmp_0
0x180068fa5  test    eax, eax
0x180068fa7  jnz     short loc_180068FCB
0x180068fa9  mov     rax, [r14+28h]
0x180068fad  cmp     byte ptr [rax+4], 0
0x180068fb1  jnz     short loc_180068FC8
0x180068fb3  mov     ebx, 0C000000Dh
0x180068fb8  mov     r9d, 85Ah
0x180068fbe  mov     ecx, 0C000000Dh
0x180068fc3  jmp     loc_180069130
0x180068fc8  add     ebp, 14h
0x180068fcb  mov     rax, [rsp+88h+arg_20]
0x180068fd3  xor     ebx, ebx
0x180068fd5  mov     [rax], ebp
0x180068fd7  test    rdi, rdi
0x180068fda  jz      loc_180069143
0x180068fe0  cmp     r15d, ebp
0x180068fe3  jnb     short loc_180068FEF
0x180068fe5  mov     ebx, 0C0000023h
0x180068fea  jmp     loc_180069143
0x180068fef  mov     eax, [r14+0Ch]
0x180068ff3  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x180068ffa  mov     rcx, rsi; String1
0x180068ffd  mov     [rdi+4], eax
0x180069000  call    wcscmp_0
0x180069005  mov     r12d, 14h
0x18006900b  test    eax, eax
0x18006900d  jz      short loc_180069076
0x18006900f  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180069016  mov     rcx, rsi; String1
0x180069019  call    wcscmp_0
0x18006901e  test    eax, eax
0x180069020  jz      short loc_180069076
0x180069022  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x180069029  mov     rcx, rsi; String1
0x18006902c  call    wcscmp_0
0x180069031  test    eax, eax
0x180069033  jz      short loc_18006905D
0x180069035  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18006903c  mov     rcx, rsi; String1
0x18006903f  call    wcscmp_0
0x180069044  test    eax, eax
0x180069046  jz      short loc_18006905D
0x180069048  mov     ebx, 0C00000BBh
0x18006904d  mov     r9d, 890h
0x180069053  mov     ecx, 0C00000BBh
0x180069058  jmp     loc_180069130
0x18006905d  mov     dword ptr [rdi], 56505344h
0x180069063  mov     rbp, r12
0x180069066  mov     eax, [r14+0Ch]
0x18006906a  lea     esi, [rax+rax*2]
0x18006906d  add     rsi, 34h ; '4'
0x180069071  add     rsi, rdi
0x180069074  jmp     short loc_180069080
0x180069076  xor     esi, esi
0x180069078  mov     dword ptr [rdi], 42505344h
0x18006907e  xor     ebp, ebp
0x180069080  mov     r15d, [r14+0Ch]
0x180069084  lea     r8, [rsp+88h+arg_0]
0x18006908c  mov     [rsp+88h+var_30], r8; __int64
0x180069091  lea     rax, [rdi+0Ch]
0x180069095  mov     [rsp+88h+var_38], r12; __int64
0x18006909a  lea     rdx, [rdi+34h]; int
0x18006909e  mov     [rsp+88h+var_40], rax; void *
0x1800690a3  lea     r9, [rdi+20h]; int
0x1800690a7  lea     rcx, [r15+rdx]
0x1800690ab  mov     [rsp+88h+var_50], 2; int
0x1800690b3  mov     [rsp+88h+var_58], r15; __int64
0x1800690b8  mov     r8d, r15d; int
0x1800690bb  mov     [rsp+88h+var_60], rcx; __int64
0x1800690c0  mov     rcx, [r14+20h]; int
0x1800690c4  mov     [rsp+88h+var_68], r12; __int64
0x1800690c9  call    SymCryptDlgroupGetValue
0x1800690ce  test    eax, eax
0x1800690d0  jz      short loc_1800690E1
0x1800690d2  mov     ecx, eax
0x1800690d4  call    SymcryptErrorCodeToNtStatus
0x1800690d9  mov     r9d, 8ABh
0x1800690df  jmp     short loc_18006912C
0x1800690e1  lea     rcx, [rdi+8]
0x1800690e5  mov     r8d, 4
0x1800690eb  lea     rdx, [rsp+88h+arg_0]
0x1800690f3  call    ReverseMemCopy
0x1800690f8  mov     r10d, [r14+0Ch]
0x1800690fc  lea     r9d, [r15+r15]
0x180069100  mov     rcx, [r14+28h]
0x180069104  add     r9, 34h ; '4'
0x180069108  add     r9, rdi
0x18006910b  mov     [rsp+88h+var_68], r10
0x180069110  mov     r8, rbp
0x180069113  mov     rdx, rsi
0x180069116  call    SymCryptDlkeyGetValue
0x18006911b  test    eax, eax
0x18006911d  jz      short loc_180069143
0x18006911f  mov     ecx, eax
0x180069121  call    SymcryptErrorCodeToNtStatus
0x180069126  mov     r9d, 8BCh
0x18006912c  mov     ecx, eax
0x18006912e  mov     ebx, eax
0x180069130  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069137  lea     rdx, aStatus; "Status"
0x18006913e  call    DebugTraceError
0x180069143  lea     r11, [rsp+88h+var_28]
0x180069148  mov     eax, ebx
0x18006914a  mov     rbx, [r11+38h]
0x18006914e  mov     rbp, [r11+40h]
0x180069152  mov     rsp, r11
0x180069155  pop     r15
0x180069157  pop     r14
0x180069159  pop     r12
0x18006915b  pop     rdi
0x18006915c  pop     rsi
0x18006915d  retn
```
