# MSCryptSetKemProperty

- ea: `0x180065260`
- end: `0x1800653cd`
- name: `MSCryptSetKemProperty`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180064094`
- `0x1800641e8`
- `0x180065260`
- `0x180065430`
- `0x1800654e0`
- `0x18007f765`

## string_xrefs

- `0x1800653ac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetKemProperty(_DWORD *a1, const wchar_t *a2, void *a3, unsigned int a4, int a5)
{
  int MlKemParamSetInfo; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  wchar_t **v13; // rdi
  wchar_t **v15; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v16[6]; // [rsp+28h] [rbp-30h] BYREF

  v16[0] = 0;
  v15 = 0;
  MlKemParamSetInfo = ValidateKemObject(a1, v16);
  v10 = MlKemParamSetInfo;
  if ( MlKemParamSetInfo < 0 )
  {
    v11 = 1042;
LABEL_3:
    v12 = (unsigned int)MlKemParamSetInfo;
LABEL_24:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v11);
    return v10;
  }
  if ( !a2 )
  {
    v11 = 1049;
LABEL_6:
    v10 = -1073741811;
    v12 = 3221225485LL;
    goto LABEL_24;
  }
  if ( a5 )
  {
    v11 = 1056;
    goto LABEL_6;
  }
  if ( wcscmp_0(a2, L"ParameterSetName") )
  {
    v11 = 1117;
    goto LABEL_23;
  }
  MlKemParamSetInfo = ValidateKemKey(a1, &v15, 0);
  v10 = MlKemParamSetInfo;
  if ( MlKemParamSetInfo < 0 )
  {
    v11 = 1065;
    goto LABEL_3;
  }
  v13 = v15;
  if ( *((_DWORD *)v15 + 4) )
  {
    v10 = -1073741816;
    v11 = 1072;
    v12 = 3221225480LL;
    goto LABEL_24;
  }
  if ( *((_DWORD *)v15 + 2) == 458753 )
  {
    v15 = 0;
    MlKemParamSetInfo = GetMlKemParamSetInfo(a3, a4, &v15);
    v10 = MlKemParamSetInfo;
    if ( MlKemParamSetInfo < 0 )
    {
      v11 = 1086;
      goto LABEL_3;
    }
  }
  else
  {
    if ( *((_DWORD *)v15 + 2) != 458754 )
    {
      v11 = 1109;
LABEL_23:
      v12 = 3221225659LL;
      v10 = -1073741637;
      goto LABEL_24;
    }
    v15 = 0;
    MlKemParamSetInfo = GetCompositeMlKemParamSetInfo(a3, a4, &v15);
    v10 = MlKemParamSetInfo;
    if ( MlKemParamSetInfo < 0 )
    {
      v11 = 1100;
      goto LABEL_3;
    }
  }
  v13[3] = (wchar_t *)v15;
  return v10;
}

```

## disassembly

```asm
0x180065260  push    rbx
0x180065262  push    rbp
0x180065263  push    rsi
0x180065264  push    rdi
0x180065265  push    r14
0x180065267  sub     rsp, 30h
0x18006526b  mov     rdi, rdx
0x18006526e  mov     [rsp+58h+var_30], 0
0x180065277  lea     rdx, [rsp+58h+var_30]
0x18006527c  mov     [rsp+58h+var_38], 0
0x180065285  mov     esi, r9d
0x180065288  mov     rbp, r8
0x18006528b  mov     r14, rcx
0x18006528e  call    ValidateKemObject
0x180065293  mov     ebx, eax
0x180065295  test    eax, eax
0x180065297  jns     short loc_1800652A6
0x180065299  mov     r9d, 412h
0x18006529f  mov     ecx, eax
0x1800652a1  jmp     loc_1800653AC
0x1800652a6  test    rdi, rdi
0x1800652a9  jnz     short loc_1800652C0
0x1800652ab  mov     r9d, 419h
0x1800652b1  mov     ebx, 0C000000Dh
0x1800652b6  mov     ecx, 0C000000Dh
0x1800652bb  jmp     loc_1800653AC
0x1800652c0  cmp     [rsp+58h+arg_20], 0
0x1800652c8  jz      short loc_1800652D2
0x1800652ca  mov     r9d, 420h
0x1800652d0  jmp     short loc_1800652B1
0x1800652d2  lea     rdx, aParametersetna; "ParameterSetName"
0x1800652d9  mov     rcx, rdi; String1
0x1800652dc  call    wcscmp_0
0x1800652e1  test    eax, eax
0x1800652e3  jnz     loc_18006539C
0x1800652e9  xor     r8d, r8d
0x1800652ec  lea     rdx, [rsp+58h+var_38]
0x1800652f1  mov     rcx, r14
0x1800652f4  call    ValidateKemKey
0x1800652f9  mov     ebx, eax
0x1800652fb  test    eax, eax
0x1800652fd  jns     short loc_180065307
0x1800652ff  mov     r9d, 429h
0x180065305  jmp     short loc_18006529F
0x180065307  mov     rdi, [rsp+58h+var_38]
0x18006530c  cmp     dword ptr [rdi+10h], 0
0x180065310  jz      short loc_180065327
0x180065312  mov     ebx, 0C0000008h
0x180065317  mov     r9d, 430h
0x18006531d  mov     ecx, 0C0000008h
0x180065322  jmp     loc_1800653AC
0x180065327  mov     ecx, [rdi+8]
0x18006532a  sub     ecx, 70001h
0x180065330  jz      short loc_180065368
0x180065332  cmp     ecx, 1
0x180065335  jz      short loc_18006533F
0x180065337  mov     r9d, 455h
0x18006533d  jmp     short loc_1800653A2
0x18006533f  lea     r8, [rsp+58h+var_38]
0x180065344  mov     [rsp+58h+var_38], 0
0x18006534d  mov     edx, esi; Size
0x18006534f  mov     rcx, rbp; Buf1
0x180065352  call    GetCompositeMlKemParamSetInfo
0x180065357  mov     ebx, eax
0x180065359  test    eax, eax
0x18006535b  jns     short loc_180065391
0x18006535d  mov     r9d, 44Ch
0x180065363  jmp     loc_18006529F
0x180065368  lea     r8, [rsp+58h+var_38]
0x18006536d  mov     [rsp+58h+var_38], 0
0x180065376  mov     edx, esi; Size
0x180065378  mov     rcx, rbp; Buf1
0x18006537b  call    GetMlKemParamSetInfo
0x180065380  mov     ebx, eax
0x180065382  test    eax, eax
0x180065384  jns     short loc_180065391
0x180065386  mov     r9d, 43Eh
0x18006538c  jmp     loc_18006529F
0x180065391  mov     rax, [rsp+58h+var_38]
0x180065396  mov     [rdi+18h], rax
0x18006539a  jmp     short loc_1800653BF
0x18006539c  mov     r9d, 45Dh
0x1800653a2  mov     ecx, 0C00000BBh
0x1800653a7  mov     ebx, 0C00000BBh
0x1800653ac  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800653b3  lea     rdx, aStatus; "Status"
0x1800653ba  call    DebugTraceError
0x1800653bf  mov     eax, ebx
0x1800653c1  add     rsp, 30h
0x1800653c5  pop     r14
0x1800653c7  pop     rdi
0x1800653c8  pop     rsi
0x1800653c9  pop     rbp
0x1800653ca  pop     rbx
0x1800653cb  retn
```
