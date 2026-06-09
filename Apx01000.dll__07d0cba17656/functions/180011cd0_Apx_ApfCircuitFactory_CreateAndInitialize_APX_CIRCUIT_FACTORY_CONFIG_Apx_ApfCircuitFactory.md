# Apx::ApfCircuitFactory::_CreateAndInitialize(_APX_CIRCUIT_FACTORY_CONFIG *,Apx::ApfCircuitFactory * *)

- ea: `0x180011cd0`
- end: `0x180011de1`
- name: `?_CreateAndInitialize@ApfCircuitFactory@Apx@@SAJPEAU_APX_CIRCUIT_FACTORY_CONFIG@@PEAPEAV12@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _APX_CIRCUIT_FACTORY_CONFIG *, struct Apx::ApfCircuitFactory **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800120f0`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x1800107d4`
- `0x180011408`
- `0x180011cd0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuitFactory::_CreateAndInitialize(
        struct _APX_CIRCUIT_FACTORY_CONFIG *a1,
        struct Apx::ApfCircuitFactory **a2)
{
  Apx::ApfCircuitFactory *v4; // rax
  Apx::ApfCircuitFactory *v5; // rbx
  int v6; // edi
  _QWORD *v7; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfCircuitFactory *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = (Apx::ApfCircuitFactory *)Apx::ApfCircuitFactory::ApfCircuitFactory(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    v6 = Apx::ApfCircuitFactory::Initialize(v5, a1);
    if ( v6 < 0 )
    {
      (**(void (__fastcall ***)(Apx::ApfCircuitFactory *, __int64))v5)(v5, 1);
    }
    else
    {
      *a2 = v5;
      v6 = 0;
    }
    goto LABEL_16;
  }
  v6 = -2147024882;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
LABEL_16:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_(v7[2], 12, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011cd0  push    rbx
0x180011cd2  push    rbp
0x180011cd3  push    rsi
0x180011cd4  push    rdi
0x180011cd5  sub     rsp, 28h
0x180011cd9  mov     rsi, rdx
0x180011cdc  mov     rdi, rcx
0x180011cdf  lea     rbp, WPP_GLOBAL_Control
0x180011ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ced  cmp     rcx, rbp
0x180011cf0  jz      short loc_180011D13
0x180011cf2  test    byte ptr [rcx+1Ch], 1
0x180011cf6  jz      short loc_180011D13
0x180011cf8  cmp     byte ptr [rcx+19h], 5
0x180011cfc  jb      short loc_180011D13
0x180011cfe  mov     edx, 0Ah
0x180011d03  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011d0a  mov     rcx, [rcx+10h]
0x180011d0e  call    WPP_SF_
0x180011d13  mov     qword ptr [rsi], 0
0x180011d1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d21  mov     ecx, 120h; unsigned __int64
0x180011d26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011d2b  mov     [rsp+48h+arg_8], rax
0x180011d30  test    rax, rax
0x180011d33  jz      short loc_180011D42
0x180011d35  mov     rcx, rax; this
0x180011d38  call    ??0ApfCircuitFactory@Apx@@AEAA@XZ; Apx::ApfCircuitFactory::ApfCircuitFactory(void)
0x180011d3d  mov     rbx, rax
0x180011d40  jmp     short loc_180011D44
0x180011d42  xor     ebx, ebx
0x180011d44  test    rbx, rbx
0x180011d47  jnz     short loc_180011D7E
0x180011d49  mov     edi, 8007000Eh
0x180011d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d55  cmp     rcx, rbp
0x180011d58  jz      short loc_180011DD6
0x180011d5a  test    byte ptr [rcx+1Ch], 20h
0x180011d5e  jz      short loc_180011DB0
0x180011d60  cmp     byte ptr [rcx+19h], 2
0x180011d64  jb      short loc_180011DB0
0x180011d66  lea     edx, [rbx+0Bh]
0x180011d69  mov     r9d, edi
0x180011d6c  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011d73  mov     rcx, [rcx+10h]
0x180011d77  call    WPP_SF_d
0x180011d7c  jmp     short loc_180011DA9
0x180011d7e  mov     rdx, rdi; struct _APX_CIRCUIT_FACTORY_CONFIG *
0x180011d81  mov     rcx, rbx; this
0x180011d84  call    ?Initialize@ApfCircuitFactory@Apx@@AEAAJPEAU_APX_CIRCUIT_FACTORY_CONFIG@@@Z; Apx::ApfCircuitFactory::Initialize(_APX_CIRCUIT_FACTORY_CONFIG *)
0x180011d89  mov     edi, eax
0x180011d8b  test    eax, eax
0x180011d8d  js      short loc_180011D96
0x180011d8f  mov     [rsi], rbx
0x180011d92  xor     edi, edi
0x180011d94  jmp     short loc_180011DA9
0x180011d96  mov     rax, [rbx]
0x180011d99  mov     edx, 1
0x180011d9e  mov     rcx, rbx
0x180011da1  mov     rax, [rax]
0x180011da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011db0  cmp     rcx, rbp
0x180011db3  jz      short loc_180011DD6
0x180011db5  test    byte ptr [rcx+1Ch], 1
0x180011db9  jz      short loc_180011DD6
0x180011dbb  cmp     byte ptr [rcx+19h], 5
0x180011dbf  jb      short loc_180011DD6
0x180011dc1  mov     edx, 0Ch
0x180011dc6  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011dcd  mov     rcx, [rcx+10h]
0x180011dd1  call    WPP_SF_
0x180011dd6  mov     eax, edi
0x180011dd8  add     rsp, 28h
0x180011ddc  pop     rdi
0x180011ddd  pop     rsi
0x180011dde  pop     rbp
0x180011ddf  pop     rbx
0x180011de0  retn
```
