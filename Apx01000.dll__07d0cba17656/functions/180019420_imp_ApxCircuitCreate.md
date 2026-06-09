# imp_ApxCircuitCreate

- ea: `0x180019420`
- end: `0x1800195e0`
- name: `imp_ApxCircuitCreate`
- size: `448`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x1800178b0`
- `0x180019420`
- `0x18002a010`

## string_xrefs

- `0x1800194e2`: `Config`
- `0x1800194fe`: `*Config`

## pseudocode

```c
__int64 __fastcall imp_ApxCircuitCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        Apx::ApfVerify *a3,
        Apx::ApfVerify *a4,
        Apx::ApfVerify *a5)
{
  Apx::ApfVerify *v9; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdi
  unsigned __int64 v18; // rax
  struct Apx::ApfCircuit *v20; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9b3c47f99e5f3ae3e284eadfa9fe0a9f_Traceguids);
  }
  v20 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull >= 0 )
  {
    IsNull = Apx::ApfVerify::IsApxInitialized(v9);
    if ( IsNull >= 0 )
    {
      IsNull = Apx::ApfVerify::ValidateClientBindings(this, v11);
      if ( IsNull >= 0 )
      {
        IsNull = Apx::ApfVerify::IsNotNull(a2, L"Factory", v12);
        if ( IsNull >= 0 )
        {
          IsNull = Apx::ApfVerify::IsNull(a3, L"Attributes", v13);
          if ( IsNull >= 0 )
          {
            IsNull = Apx::ApfVerify::IsNotNull(a4, L"Config", v14);
            if ( IsNull >= 0 )
            {
              IsNull = Apx::ApfVerify::IsNotNull(*(Apx::ApfVerify **)a4, L"*Config", v15);
              if ( IsNull >= 0 )
              {
                IsNull = Apx::ApfVerify::IsNotNull(a5, L"Circuit", v16);
                if ( IsNull >= 0 )
                {
                  *(_QWORD *)a5 = 0;
                  v17 = ~*(_QWORD *)a4;
                  IsNull = Apx::ApfCircuit::_CreateAndInitialize(
                             (struct Apx::ApfCircuitFactory *)~(unsigned __int64)a2,
                             (struct Apx::ApfCircuitInit *)v17,
                             &v20);
                  if ( IsNull < 0 )
                  {
                    if ( v20 )
                      (**(void (__fastcall ***)(struct Apx::ApfCircuit *, __int64))v20)(v20, 1);
                  }
                  else
                  {
                    v18 = ~(unsigned __int64)v20;
                    *(_QWORD *)a5 = ~(unsigned __int64)v20;
                    *(_QWORD *)(v17 + 120) = v18;
                    *(_QWORD *)a4 = 0;
                    if ( (*(_BYTE *)(v17 + 24) & 1) == 0 )
                      (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
                    IsNull = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9b3c47f99e5f3ae3e284eadfa9fe0a9f_Traceguids);
  }
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x180019420  push    rbx
0x180019422  push    rbp
0x180019423  push    rsi
0x180019424  push    rdi
0x180019425  push    r13
0x180019427  push    r14
0x180019429  sub     rsp, 38h
0x18001942d  mov     r14, r9
0x180019430  mov     rsi, r8
0x180019433  mov     rbp, rdx
0x180019436  mov     rdi, rcx
0x180019439  mov     rcx, cs:WPP_GLOBAL_Control
0x180019440  lea     r13, WPP_GLOBAL_Control
0x180019447  cmp     rcx, r13
0x18001944a  jz      short loc_18001946D
0x18001944c  test    byte ptr [rcx+1Ch], 1
0x180019450  jz      short loc_18001946D
0x180019452  cmp     byte ptr [rcx+19h], 5
0x180019456  jb      short loc_18001946D
0x180019458  mov     rcx, [rcx+10h]
0x18001945c  lea     r8, WPP_9b3c47f99e5f3ae3e284eadfa9fe0a9f_Traceguids
0x180019463  mov     edx, 0Ah
0x180019468  call    WPP_SF_
0x18001946d  lea     rdx, aGlobals; "Globals"
0x180019474  mov     [rsp+68h+var_48], 0
0x18001947d  mov     rcx, rdi; this
0x180019480  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x180019485  mov     ebx, eax
0x180019487  test    eax, eax
0x180019489  js      loc_1800195A4
0x18001948f  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x180019494  mov     ebx, eax
0x180019496  test    eax, eax
0x180019498  js      loc_1800195A4
0x18001949e  mov     rcx, rdi; this
0x1800194a1  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x1800194a6  mov     ebx, eax
0x1800194a8  test    eax, eax
0x1800194aa  js      loc_1800195A4
0x1800194b0  lea     rdx, aFactory; "Factory"
0x1800194b7  mov     rcx, rbp; this
0x1800194ba  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800194bf  mov     ebx, eax
0x1800194c1  test    eax, eax
0x1800194c3  js      loc_1800195A4
0x1800194c9  lea     rdx, aAttributes; "Attributes"
0x1800194d0  mov     rcx, rsi; this
0x1800194d3  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x1800194d8  mov     ebx, eax
0x1800194da  test    eax, eax
0x1800194dc  js      loc_1800195A4
0x1800194e2  lea     rdx, aConfig_0; "Config"
0x1800194e9  mov     rcx, r14; this
0x1800194ec  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800194f1  mov     ebx, eax
0x1800194f3  test    eax, eax
0x1800194f5  js      loc_1800195A4
0x1800194fb  mov     rcx, [r14]; this
0x1800194fe  lea     rdx, aConfig; "*Config"
0x180019505  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001950a  mov     ebx, eax
0x18001950c  test    eax, eax
0x18001950e  js      loc_1800195A4
0x180019514  mov     rsi, [rsp+68h+arg_20]
0x18001951c  lea     rdx, aCircuit; "Circuit"
0x180019523  mov     rcx, rsi; this
0x180019526  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001952b  mov     ebx, eax
0x18001952d  test    eax, eax
0x18001952f  js      short loc_1800195A4
0x180019531  mov     qword ptr [rsi], 0
0x180019538  lea     r8, [rsp+68h+var_48]; struct Apx::ApfCircuit **
0x18001953d  mov     rdi, [r14]
0x180019540  not     rbp
0x180019543  not     rdi
0x180019546  mov     rcx, rbp; struct Apx::ApfCircuitFactory *
0x180019549  mov     rdx, rdi; struct Apx::ApfCircuitInit *
0x18001954c  call    ?_CreateAndInitialize@ApfCircuit@Apx@@SAJPEAVApfCircuitFactory@2@PEAVApfCircuitInit@2@PEAPEAV12@@Z; Apx::ApfCircuit::_CreateAndInitialize(Apx::ApfCircuitFactory *,Apx::ApfCircuitInit *,Apx::ApfCircuit * *)
0x180019551  mov     ebx, eax
0x180019553  test    eax, eax
0x180019555  js      short loc_18001958A
0x180019557  mov     rax, [rsp+68h+var_48]
0x18001955c  not     rax
0x18001955f  mov     [rsi], rax
0x180019562  mov     [rdi+78h], rax
0x180019566  mov     qword ptr [r14], 0
0x18001956d  test    byte ptr [rdi+18h], 1
0x180019571  jnz     short loc_180019586
0x180019573  mov     rax, [rdi]
0x180019576  mov     edx, 1
0x18001957b  mov     rcx, rdi
0x18001957e  mov     rax, [rax]
0x180019581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019586  xor     ebx, ebx
0x180019588  jmp     short loc_1800195A4
0x18001958a  mov     rcx, [rsp+68h+var_48]
0x18001958f  test    rcx, rcx
0x180019592  jz      short loc_1800195A4
0x180019594  mov     rax, [rcx]
0x180019597  mov     edx, 1
0x18001959c  mov     rax, [rax]
0x18001959f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195ab  cmp     rcx, r13
0x1800195ae  jz      short loc_1800195D1
0x1800195b0  test    byte ptr [rcx+1Ch], 1
0x1800195b4  jz      short loc_1800195D1
0x1800195b6  cmp     byte ptr [rcx+19h], 5
0x1800195ba  jb      short loc_1800195D1
0x1800195bc  mov     rcx, [rcx+10h]
0x1800195c0  lea     r8, WPP_9b3c47f99e5f3ae3e284eadfa9fe0a9f_Traceguids
0x1800195c7  mov     edx, 0Bh
0x1800195cc  call    WPP_SF_
0x1800195d1  mov     eax, ebx
0x1800195d3  add     rsp, 38h
0x1800195d7  pop     r14
0x1800195d9  pop     r13
0x1800195db  pop     rdi
0x1800195dc  pop     rsi
0x1800195dd  pop     rbp
0x1800195de  pop     rbx
0x1800195df  retn
```
