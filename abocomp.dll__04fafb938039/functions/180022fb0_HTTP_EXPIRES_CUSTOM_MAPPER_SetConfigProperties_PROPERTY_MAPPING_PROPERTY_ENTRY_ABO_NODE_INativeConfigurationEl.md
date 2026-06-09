# HTTP_EXPIRES_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022fb0`
- end: `0x18002317d`
- name: `?SetConfigProperties@HTTP_EXPIRES_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(HTTP_EXPIRES_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180022fb0`
- `0x180029af8`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023114`
- `msvcrt!_wcsicmp` at `0x180023114`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022ff6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022ff6`

## string_xrefs

- `0x180023017`: `cacheControlMode`
- `0x18002305b`: `cacheControlMode`
- `0x1800230a3`: `cacheControlMode`
- `0x180023145`: `cacheControlMaxAge`

## pseudocode

```c
__int64 __fastcall HTTP_EXPIRES_CUSTOM_MAPPER::SetConfigProperties(
        HTTP_EXPIRES_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  struct INativeConfigurationElement *v5; // rbx
  __int64 v6; // rdi
  _WORD *v7; // rsi
  __int64 result; // rax
  const wchar_t *v9; // rdi
  unsigned int v10; // edx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r9
  const wchar_t *v15; // rdx
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v16 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  if ( !a4 )
    return 2147942487LL;
  v5 = a5;
  if ( !a5 )
    return 2147942487LL;
  v6 = -1;
  v7 = (_WORD *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
  do
    ++v6;
  while ( v7[v6] );
  if ( !(_DWORD)v6 )
    return (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v5 + 112LL))(
             v5,
             L"cacheControlMode",
             0,
             0);
  if ( ((*v7 - 68) & 0xFFDF) != 0 )
  {
    if ( *v7 == 83 || (result = 0, *v7 == 115) )
    {
      result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64))(*(_QWORD *)v5 + 112LL))(
                 v5,
                 L"cacheControlMode",
                 3);
      if ( (int)result >= 0 )
      {
        if ( (unsigned int)v6 > 2 )
          return (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _WORD *, _QWORD))(*(_QWORD *)v5 + 128LL))(
                   v5,
                   L"httpExpires",
                   v7 + 2,
                   0);
        return 2147942487LL;
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64))(*(_QWORD *)v5 + 112LL))(
               v5,
               L"cacheControlMode",
               2);
    if ( (int)result < 0 )
      return result;
    if ( (unsigned int)v6 <= 2 )
      return 2147942487LL;
    v9 = v7 + 2;
    v10 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    if ( v11 )
    {
      do
      {
        if ( *v9 == 32 || *v9 == 9 )
          ++v9;
        ++v10;
        v12 = -1;
        do
          ++v12;
        while ( v9[v12] );
      }
      while ( v10 < v12 );
    }
    v13 = _wcsicmp(v9, L"0xFFFFFFFF");
    v14 = 0;
    v15 = L"Infinite";
    if ( v13 )
      v15 = v9;
    LOBYTE(v14) = v13 == 0;
    result = TIMESPAN_PARSER::ParseFromString(&v16, v15, 1, v14);
    if ( (int)result >= 0 )
      return (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v5 + 144LL))(
               v5,
               L"cacheControlMaxAge",
               v16,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x180022fb0  mov     [rsp+arg_0], rbx
0x180022fb5  mov     [rsp+arg_10], rbp
0x180022fba  push    rsi
0x180022fbb  push    rdi
0x180022fbc  push    r14
0x180022fbe  sub     rsp, 30h
0x180022fc2  xor     ebp, ebp
0x180022fc4  mov     [rsp+48h+arg_8], rbp
0x180022fc9  test    rdx, rdx
0x180022fcc  jz      loc_180023165
0x180022fd2  test    r8, r8
0x180022fd5  jz      loc_180023165
0x180022fdb  test    r9, r9
0x180022fde  jz      loc_180023165
0x180022fe4  mov     rbx, [rsp+48h+arg_20]
0x180022fe9  test    rbx, rbx
0x180022fec  jz      loc_180023165
0x180022ff2  lea     rcx, [r8+10h]
0x180022ff6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022ffc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180023000  mov     rdi, r14
0x180023003  mov     rsi, [rax+18h]
0x180023007  inc     rdi
0x18002300a  cmp     [rsi+rdi*2], bp
0x18002300e  jnz     short loc_180023007
0x180023010  test    edi, edi
0x180023012  jnz     short loc_180023035
0x180023014  mov     rax, [rbx]
0x180023017  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x18002301e  xor     r9d, r9d
0x180023021  xor     r8d, r8d
0x180023024  mov     rcx, rbx
0x180023027  mov     rax, [rax+70h]
0x18002302b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023030  jmp     loc_18002316A
0x180023035  movzx   eax, word ptr [rsi]
0x180023038  mov     ecx, 0FFDFh
0x18002303d  sub     ax, 44h ; 'D'
0x180023041  test    cx, ax
0x180023044  jz      short loc_1800230A0
0x180023046  cmp     word ptr [rsi], 53h ; 'S'
0x18002304a  jz      short loc_180023058
0x18002304c  cmp     word ptr [rsi], 73h ; 's'
0x180023050  mov     eax, ebp
0x180023052  jnz     loc_18002316A
0x180023058  mov     rax, [rbx]
0x18002305b  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x180023062  xor     r9d, r9d
0x180023065  mov     rcx, rbx
0x180023068  mov     rax, [rax+70h]
0x18002306c  lea     r8d, [r9+3]
0x180023070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023075  test    eax, eax
0x180023077  js      loc_18002316A
0x18002307d  cmp     edi, 2
0x180023080  jbe     loc_180023165
0x180023086  mov     rax, [rbx]
0x180023089  lea     r8, [rsi+4]
0x18002308d  lea     rdx, aHttpexpires; "httpExpires"
0x180023094  mov     rax, [rax+80h]
0x18002309b  jmp     loc_180023158
0x1800230a0  mov     rax, [rbx]
0x1800230a3  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x1800230aa  xor     r9d, r9d
0x1800230ad  mov     rcx, rbx
0x1800230b0  mov     rax, [rax+70h]
0x1800230b4  lea     r8d, [r9+2]
0x1800230b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230bd  test    eax, eax
0x1800230bf  js      loc_18002316A
0x1800230c5  cmp     edi, 2
0x1800230c8  jbe     loc_180023165
0x1800230ce  lea     rdi, [rsi+4]
0x1800230d2  mov     edx, ebp
0x1800230d4  mov     rax, r14
0x1800230d7  inc     rax
0x1800230da  cmp     [rdi+rax*2], bp
0x1800230de  jnz     short loc_1800230D7
0x1800230e0  test    rax, rax
0x1800230e3  jz      short loc_18002310A
0x1800230e5  cmp     word ptr [rdi], 20h ; ' '
0x1800230e9  jz      short loc_1800230F1
0x1800230eb  cmp     word ptr [rdi], 9
0x1800230ef  jnz     short loc_1800230F5
0x1800230f1  add     rdi, 2
0x1800230f5  inc     edx
0x1800230f7  mov     rcx, r14
0x1800230fa  inc     rcx
0x1800230fd  cmp     [rdi+rcx*2], bp
0x180023101  jnz     short loc_1800230FA
0x180023103  mov     eax, edx
0x180023105  cmp     rax, rcx
0x180023108  jb      short loc_1800230E5
0x18002310a  lea     rdx, a0xffffffff; "0xFFFFFFFF"
0x180023111  mov     rcx, rdi; String1
0x180023114  call    cs:__imp__wcsicmp
0x18002311a  mov     r9d, ebp
0x18002311d  lea     rdx, aInfinite; "Infinite"
0x180023124  test    eax, eax
0x180023126  lea     rcx, [rsp+48h+arg_8]
0x18002312b  mov     r8d, 1
0x180023131  cmovnz  rdx, rdi
0x180023135  setz    r9b
0x180023139  call    ?ParseFromString@TIMESPAN_PARSER@@QEAAJPEBGW4TIMESPAN_FORMAT@@H@Z; TIMESPAN_PARSER::ParseFromString(ushort const *,TIMESPAN_FORMAT,int)
0x18002313e  test    eax, eax
0x180023140  js      short loc_18002316A
0x180023142  mov     rax, [rbx]
0x180023145  lea     rdx, aCachecontrolma; "cacheControlMaxAge"
0x18002314c  mov     r8, [rsp+48h+arg_8]
0x180023151  mov     rax, [rax+90h]
0x180023158  mov     rcx, rbx
0x18002315b  xor     r9d, r9d
0x18002315e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023163  jmp     short loc_18002316A
0x180023165  mov     eax, 80070057h
0x18002316a  mov     rbx, [rsp+48h+arg_0]
0x18002316f  mov     rbp, [rsp+48h+arg_10]
0x180023174  add     rsp, 30h
0x180023178  pop     r14
0x18002317a  pop     rdi
0x18002317b  pop     rsi
0x18002317c  retn
```
