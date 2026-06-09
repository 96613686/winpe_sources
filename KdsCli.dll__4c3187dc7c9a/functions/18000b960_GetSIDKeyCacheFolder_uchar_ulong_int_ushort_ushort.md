# GetSIDKeyCacheFolder(uchar *,ulong,int,ushort * *,ushort * *)

- ea: `0x18000b960`
- end: `0x18000bb2a`
- name: `?GetSIDKeyCacheFolder@@YAJPEAEKHPEAPEAG1@Z`
- size: `458`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, int@<r8d>, unsigned __int16 **@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800187ec`

## callees

- `0x18000b758`
- `0x18000b960`
- `0x18000be6c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x18000b9d5`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000ba17`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall GetSIDKeyCacheFolder(
        PUCHAR pbInput,
        ULONG cbInput,
        int a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  char *v8; // rbx
  int UserStorageArea; // eax
  void *v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // rax
  size_t v13; // r14
  signed int HashOfSecruityDescr; // eax
  _OWORD *v15; // rbp
  void *Src; // [rsp+20h] [rbp-58h] BYREF
  void *lpMem; // [rsp+28h] [rbp-50h] BYREF

  Src = 0;
  lpMem = 0;
  v8 = 0;
  UserStorageArea = GetUserStorageArea(0, a3, &Src);
  v10 = Src;
  v11 = UserStorageArea;
  if ( UserStorageArea >= 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)Src + v12) );
    v13 = 2 * v12;
    v8 = (char *)SIDKeyProvAlloc(2 * v12 + 182);
    if ( v8 )
    {
      HashOfSecruityDescr = GetHashOfSecruityDescr(pbInput, cbInput, (WCHAR **)&lpMem);
      v15 = lpMem;
      v11 = HashOfSecruityDescr;
      if ( HashOfSecruityDescr >= 0 )
      {
        memcpy_0(v8, v10, v13);
        wmemcpy((wchar_t *)&v8[v13], L"\\Microsoft\\Crypto\\KdsKey\\", 25);
        *(_OWORD *)&v8[v13 + 50] = *v15;
        *(_OWORD *)&v8[v13 + 66] = v15[1];
        *(_OWORD *)&v8[v13 + 82] = v15[2];
        *(_OWORD *)&v8[v13 + 98] = v15[3];
        *(_OWORD *)&v8[v13 + 114] = v15[4];
        *(_OWORD *)&v8[v13 + 130] = v15[5];
        *(_OWORD *)&v8[v13 + 146] = v15[6];
        *(_OWORD *)&v8[v13 + 162] = v15[7];
        *(_WORD *)&v8[v13 + 178] = *((_WORD *)v15 + 64);
        *a5 = (unsigned __int16 *)v8;
        v8 = 0;
        *a4 = (unsigned __int16 *)v10;
        v10 = 0;
      }
      else
      {
        SidKeyDebugTraceError(
          HashOfSecruityDescr,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
          0x12Cu);
      }
      if ( v15 )
        SIDKeyProvFree(v15);
    }
    else
    {
      v11 = -2147024882;
      SidKeyDebugTraceError(
        0x8007000E,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x121u);
    }
  }
  if ( v10 )
    SIDKeyProvFree(v10);
  if ( v8 )
    SIDKeyProvFree(v8);
  return v11;
}

```

## disassembly

```asm
0x18000b960  push    rbx
0x18000b962  push    rbp
0x18000b963  push    rsi
0x18000b964  push    rdi
0x18000b965  push    r12
0x18000b967  push    r13
0x18000b969  push    r14
0x18000b96b  push    r15
0x18000b96d  sub     rsp, 38h
0x18000b971  mov     eax, r8d
0x18000b974  xor     r13d, r13d
0x18000b977  mov     ebp, edx
0x18000b979  mov     [rsp+78h+Src], r13
0x18000b97e  mov     r15, rcx
0x18000b981  mov     [rsp+78h+lpMem], r13
0x18000b986  mov     edx, eax
0x18000b988  lea     r8, [rsp+78h+Src]
0x18000b98d  xor     ecx, ecx
0x18000b98f  mov     r12, r9
0x18000b992  mov     ebx, r13d
0x18000b995  call    GetUserStorageArea
0x18000b99a  mov     rsi, [rsp+78h+Src]
0x18000b99f  mov     edi, eax
0x18000b9a1  test    eax, eax
0x18000b9a3  js      loc_18000BAFD
0x18000b9a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b9ad  inc     rax
0x18000b9b0  cmp     [rsi+rax*2], r13w
0x18000b9b5  jnz     short loc_18000B9AD
0x18000b9b7  lea     r14, [rax+rax]
0x18000b9bb  lea     rcx, [r14+0B6h]; unsigned __int64
0x18000b9c2  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000b9c7  mov     rbx, rax
0x18000b9ca  test    rax, rax
0x18000b9cd  jnz     short loc_18000B9F7
0x18000b9cf  mov     r9d, 121h; unsigned int
0x18000b9d5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b9dc  lea     rdx, aHr; "hr"
0x18000b9e3  mov     ecx, 8007000Eh; unsigned int
0x18000b9e8  mov     edi, 8007000Eh
0x18000b9ed  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b9f2  jmp     loc_18000BAFD
0x18000b9f7  lea     r8, [rsp+78h+lpMem]
0x18000b9fc  mov     edx, ebp; cbInput
0x18000b9fe  mov     rcx, r15; pbInput
0x18000ba01  call    GetHashOfSecruityDescr
0x18000ba06  mov     rbp, [rsp+78h+lpMem]
0x18000ba0b  mov     edi, eax
0x18000ba0d  test    eax, eax
0x18000ba0f  jns     short loc_18000BA31
0x18000ba11  mov     r9d, 12Ch; unsigned int
0x18000ba17  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000ba1e  lea     rdx, aHr; "hr"
0x18000ba25  mov     ecx, eax; unsigned int
0x18000ba27  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000ba2c  jmp     loc_18000BAF0
0x18000ba31  mov     r8, r14; Size
0x18000ba34  mov     rdx, rsi; Src
0x18000ba37  mov     rcx, rbx; void *
0x18000ba3a  call    memcpy_0
0x18000ba3f  movups  xmm0, xmmword ptr cs:aMicrosoftCrypt; "\\Microsoft\\Crypto\\KdsKey\\"
0x18000ba46  movups  xmmword ptr [r14+rbx], xmm0
0x18000ba4b  movups  xmm1, xmmword ptr cs:aMicrosoftCrypt+10h; "ft\\Crypto\\KdsKey\\"
0x18000ba52  movups  xmmword ptr [r14+rbx+10h], xmm1
0x18000ba58  movups  xmm0, xmmword ptr cs:aMicrosoftCrypt+20h; "o\\KdsKey\\"
0x18000ba5f  movups  xmmword ptr [r14+rbx+20h], xmm0
0x18000ba65  movzx   eax, word ptr cs:aMicrosoftCrypt+30h; "\\"
0x18000ba6c  mov     [r14+rbx+30h], ax
0x18000ba72  movups  xmm0, xmmword ptr [rbp+0]
0x18000ba76  movups  xmmword ptr [r14+rbx+32h], xmm0
0x18000ba7c  movups  xmm1, xmmword ptr [rbp+10h]
0x18000ba80  movups  xmmword ptr [r14+rbx+42h], xmm1
0x18000ba86  movups  xmm0, xmmword ptr [rbp+20h]
0x18000ba8a  movups  xmmword ptr [r14+rbx+52h], xmm0
0x18000ba90  movups  xmm1, xmmword ptr [rbp+30h]
0x18000ba94  movups  xmmword ptr [r14+rbx+62h], xmm1
0x18000ba9a  movups  xmm0, xmmword ptr [rbp+40h]
0x18000ba9e  movups  xmmword ptr [r14+rbx+72h], xmm0
0x18000baa4  movups  xmm1, xmmword ptr [rbp+50h]
0x18000baa8  movups  xmmword ptr [r14+rbx+82h], xmm1
0x18000bab1  movups  xmm0, xmmword ptr [rbp+60h]
0x18000bab5  movups  xmmword ptr [r14+rbx+92h], xmm0
0x18000babe  movups  xmm1, xmmword ptr [rbp+70h]
0x18000bac2  movups  xmmword ptr [r14+rbx+0A2h], xmm1
0x18000bacb  movzx   eax, word ptr [rbp+80h]
0x18000bad2  mov     [r14+rbx+0B2h], ax
0x18000badb  mov     rax, [rsp+78h+arg_20]
0x18000bae3  mov     [rax], rbx
0x18000bae6  mov     rbx, r13
0x18000bae9  mov     [r12], rsi
0x18000baed  mov     rsi, r13
0x18000baf0  test    rbp, rbp
0x18000baf3  jz      short loc_18000BAFD
0x18000baf5  mov     rcx, rbp; lpMem
0x18000baf8  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000bafd  test    rsi, rsi
0x18000bb00  jz      short loc_18000BB0A
0x18000bb02  mov     rcx, rsi; lpMem
0x18000bb05  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000bb0a  test    rbx, rbx
0x18000bb0d  jz      short loc_18000BB17
0x18000bb0f  mov     rcx, rbx; lpMem
0x18000bb12  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000bb17  mov     eax, edi
0x18000bb19  add     rsp, 38h
0x18000bb1d  pop     r15
0x18000bb1f  pop     r14
0x18000bb21  pop     r13
0x18000bb23  pop     r12
0x18000bb25  pop     rdi
0x18000bb26  pop     rsi
0x18000bb27  pop     rbp
0x18000bb28  pop     rbx
0x18000bb29  retn
```
