# imp_ApxCircuitFactoryCreate

- ea: `0x1800120f0`
- end: `0x180012331`
- name: `imp_ApxCircuitFactoryCreate`
- size: `577`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_CIRCUIT_FACTORY_CONFIG *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x180011cd0`
- `0x1800120f0`
- `0x18002a010`

## string_xrefs

- `0x18001219e`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxCircuitFactoryCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_CIRCUIT_FACTORY_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // r9
  _DWORD *v16; // rax
  struct Apx::ApfCircuitFactory *v18; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids);
  }
  v18 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_32;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_32;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_32;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_32;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_32;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Factory", v13);
  if ( IsNull < 0 )
    goto LABEL_32;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 24 )
  {
    v15 = *((unsigned int *)a3 + 1);
    if ( (v15 & 0xFFFFFFFE) != 0 )
    {
      IsNull = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_33;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids, v15, 1);
    }
    else
    {
      v16 = (_DWORD *)*((_QWORD *)a3 + 2);
      if ( !v16 || *v16 == 24 )
      {
        IsNull = Apx::ApfCircuitFactory::_CreateAndInitialize(a3, &v18);
        if ( IsNull < 0 )
        {
          if ( v18 )
            (**(void (__fastcall ***)(struct Apx::ApfCircuitFactory *, __int64))v18)(v18, 1);
        }
        else
        {
          IsNull = 0;
          *(_QWORD *)a4 = ~(unsigned __int64)v18;
        }
      }
      else
      {
        IsNull = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_33;
        WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids, 24, *v16);
      }
    }
    goto LABEL_32;
  }
  IsNull = -2147024809;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids,
      24,
      *(_DWORD *)a3);
LABEL_32:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    WPP_SF_(v14[2], 14, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x1800120f0  push    rbx
0x1800120f2  push    rbp
0x1800120f3  push    rsi
0x1800120f4  push    rdi
0x1800120f5  push    r12
0x1800120f7  push    r14
0x1800120f9  push    r15
0x1800120fb  sub     rsp, 40h
0x1800120ff  mov     rsi, r9
0x180012102  mov     rdi, r8
0x180012105  mov     r14, rdx
0x180012108  mov     rbp, rcx
0x18001210b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012112  lea     r15, WPP_GLOBAL_Control
0x180012119  lea     r12, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids
0x180012120  cmp     rcx, r15
0x180012123  jz      short loc_180012142
0x180012125  test    byte ptr [rcx+1Ch], 1
0x180012129  jz      short loc_180012142
0x18001212b  cmp     byte ptr [rcx+19h], 5
0x18001212f  jb      short loc_180012142
0x180012131  mov     rcx, [rcx+10h]
0x180012135  mov     edx, 0Ah
0x18001213a  mov     r8, r12
0x18001213d  call    WPP_SF_
0x180012142  lea     rdx, aGlobals; "Globals"
0x180012149  mov     [rsp+78h+var_48], 0
0x180012152  mov     rcx, rbp; this
0x180012155  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001215a  mov     ebx, eax
0x18001215c  test    eax, eax
0x18001215e  js      loc_1800122F7
0x180012164  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x180012169  mov     ebx, eax
0x18001216b  test    eax, eax
0x18001216d  js      loc_1800122F7
0x180012173  mov     rcx, rbp; this
0x180012176  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18001217b  mov     ebx, eax
0x18001217d  test    eax, eax
0x18001217f  js      loc_1800122F7
0x180012185  lea     rdx, aAttributes; "Attributes"
0x18001218c  mov     rcx, r14; this
0x18001218f  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x180012194  mov     ebx, eax
0x180012196  test    eax, eax
0x180012198  js      loc_1800122F7
0x18001219e  lea     rdx, aConfig_0; "Config"
0x1800121a5  mov     rcx, rdi; this
0x1800121a8  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800121ad  mov     ebx, eax
0x1800121af  test    eax, eax
0x1800121b1  js      loc_1800122F7
0x1800121b7  lea     rdx, aFactory; "Factory"
0x1800121be  mov     rcx, rsi; this
0x1800121c1  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800121c6  mov     ebx, eax
0x1800121c8  test    eax, eax
0x1800121ca  js      loc_1800122F7
0x1800121d0  mov     qword ptr [rsi], 0
0x1800121d7  mov     r10d, 18h
0x1800121dd  mov     eax, [rdi]
0x1800121df  cmp     eax, r10d
0x1800121e2  jz      short loc_180012229
0x1800121e4  mov     ebx, 80070057h
0x1800121e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121f0  cmp     rcx, r15
0x1800121f3  jz      loc_180012320
0x1800121f9  test    byte ptr [rcx+1Ch], 20h
0x1800121fd  jz      loc_1800122FE
0x180012203  cmp     byte ptr [rcx+19h], 2
0x180012207  jb      loc_1800122FE
0x18001220d  lea     edx, [r10-0Dh]
0x180012211  mov     [rsp+78h+var_58], eax
0x180012215  mov     rcx, [rcx+10h]
0x180012219  mov     r9d, r10d
0x18001221c  mov     r8, r12
0x18001221f  call    WPP_SF_DDd
0x180012224  jmp     loc_1800122F7
0x180012229  mov     r9d, [rdi+4]
0x18001222d  test    r9d, 0FFFFFFFEh
0x180012234  jz      short loc_18001227A
0x180012236  mov     ebx, 80070057h
0x18001223b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012242  cmp     rcx, r15
0x180012245  jz      loc_180012320
0x18001224b  test    byte ptr [rcx+1Ch], 20h
0x18001224f  jz      loc_1800122FE
0x180012255  cmp     byte ptr [rcx+19h], 2
0x180012259  jb      loc_1800122FE
0x18001225f  mov     rcx, [rcx+10h]
0x180012263  mov     edx, 0Ch
0x180012268  mov     r8, r12
0x18001226b  mov     [rsp+78h+var_58], 1
0x180012273  call    WPP_SF_DDd
0x180012278  jmp     short loc_1800122F7
0x18001227a  mov     rax, [rdi+10h]
0x18001227e  test    rax, rax
0x180012281  jz      short loc_1800122BB
0x180012283  mov     r8d, [rax]
0x180012286  cmp     r8d, r10d
0x180012289  jz      short loc_1800122BB
0x18001228b  mov     ebx, 80070057h
0x180012290  mov     rcx, cs:WPP_GLOBAL_Control
0x180012297  cmp     rcx, r15
0x18001229a  jz      loc_180012320
0x1800122a0  test    byte ptr [rcx+1Ch], 20h
0x1800122a4  jz      short loc_1800122FE
0x1800122a6  cmp     byte ptr [rcx+19h], 2
0x1800122aa  jb      short loc_1800122FE
0x1800122ac  mov     edx, 0Dh
0x1800122b1  mov     [rsp+78h+var_58], r8d
0x1800122b6  jmp     loc_180012215
0x1800122bb  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfCircuitFactory **
0x1800122c0  mov     rcx, rdi; struct _APX_CIRCUIT_FACTORY_CONFIG *
0x1800122c3  call    ?_CreateAndInitialize@ApfCircuitFactory@Apx@@SAJPEAU_APX_CIRCUIT_FACTORY_CONFIG@@PEAPEAV12@@Z; Apx::ApfCircuitFactory::_CreateAndInitialize(_APX_CIRCUIT_FACTORY_CONFIG *,Apx::ApfCircuitFactory * *)
0x1800122c8  mov     ebx, eax
0x1800122ca  test    eax, eax
0x1800122cc  js      short loc_1800122DD
0x1800122ce  mov     rax, [rsp+78h+var_48]
0x1800122d3  xor     ebx, ebx
0x1800122d5  not     rax
0x1800122d8  mov     [rsi], rax
0x1800122db  jmp     short loc_1800122F7
0x1800122dd  mov     rcx, [rsp+78h+var_48]
0x1800122e2  test    rcx, rcx
0x1800122e5  jz      short loc_1800122F7
0x1800122e7  mov     rax, [rcx]
0x1800122ea  mov     edx, 1
0x1800122ef  mov     rax, [rax]
0x1800122f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122fe  cmp     rcx, r15
0x180012301  jz      short loc_180012320
0x180012303  test    byte ptr [rcx+1Ch], 1
0x180012307  jz      short loc_180012320
0x180012309  cmp     byte ptr [rcx+19h], 5
0x18001230d  jb      short loc_180012320
0x18001230f  mov     rcx, [rcx+10h]
0x180012313  mov     edx, 0Eh
0x180012318  mov     r8, r12
0x18001231b  call    WPP_SF_
0x180012320  mov     eax, ebx
0x180012322  add     rsp, 40h
0x180012326  pop     r15
0x180012328  pop     r14
0x18001232a  pop     r12
0x18001232c  pop     rdi
0x18001232d  pop     rsi
0x18001232e  pop     rbp
0x18001232f  pop     rbx
0x180012330  retn
```
