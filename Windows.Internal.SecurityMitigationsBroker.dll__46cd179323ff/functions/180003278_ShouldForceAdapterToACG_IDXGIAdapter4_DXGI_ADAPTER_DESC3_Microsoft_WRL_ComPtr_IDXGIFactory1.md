# ShouldForceAdapterToACG(IDXGIAdapter4 *,DXGI_ADAPTER_DESC3 *,Microsoft::WRL::ComPtr<IDXGIFactory1>)

- ea: `0x180003278`
- end: `0x180003426`
- name: `?ShouldForceAdapterToACG@@YA_NPEAUIDXGIAdapter4@@PEAUDXGI_ADAPTER_DESC3@@V?$ComPtr@UIDXGIFactory1@@@WRL@Microsoft@@@Z`
- size: `430`
- prototype: `char __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800026f4`

## callees

- `0x180003278`
- `0x180006956`
- `0x180006980`
- `0x180007010`

## pseudocode

```c
char __fastcall ShouldForceAdapterToACG(__int64 *a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  void (*v7)(void); // rax
  int v8; // edi
  unsigned int i; // esi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[256]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+160h] [rbp+60h]
  int v20; // [rsp+164h] [rbp+64h]

  if ( (*(_BYTE *)(a2 + 304) & 4) == 0 && *(_DWORD *)(a2 + 256) == 32902 )
  {
    v5 = *a1;
    memset(v17, 0, sizeof(v17));
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64, _OWORD *))(v5 + 112))(a1, 0, 1, v17) >= 0 )
    {
      v6 = *a3;
      if ( *a3 )
      {
        *a3 = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
LABEL_21:
        v7();
        return 1;
      }
      return 1;
    }
    if ( (*(_BYTE *)(a2 + 304) & 0x20) != 0 )
    {
      v8 = 0;
      for ( i = 0; ; ++i )
      {
        v10 = *a3;
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 56LL))(v10, i, &v16) < 0 )
          break;
        memset_0(v18, 0, 0x130u);
        if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v16 + 64LL))(v16, v18) < 0
          || v19 != 5140
          || v20 != 140 )
        {
          ++v8;
        }
        v11 = v16;
        if ( v16 )
        {
          v16 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      v12 = v16;
      if ( v16 )
      {
        v16 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      if ( v8 == 1 )
      {
        v13 = *a3;
        if ( *a3 )
        {
          *a3 = 0;
          v7 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
          goto LABEL_21;
        }
        return 1;
      }
    }
  }
  v15 = *a3;
  if ( *a3 )
  {
    *a3 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180003278  mov     [rsp-8+arg_8], rbx
0x18000327d  push    rbp
0x18000327e  push    rsi
0x18000327f  push    rdi
0x180003280  lea     rbp, [rsp-0A0h]
0x180003288  sub     rsp, 1A0h
0x18000328f  mov     rax, cs:__security_cookie
0x180003296  xor     rax, rsp
0x180003299  mov     [rbp+0B0h+var_20], rax
0x1800032a0  test    byte ptr [rdx+130h], 4
0x1800032a7  mov     rbx, r8
0x1800032aa  mov     rdi, rdx
0x1800032ad  jnz     loc_1800033E7
0x1800032b3  cmp     dword ptr [rdx+100h], 8086h
0x1800032bd  jnz     loc_1800033E7
0x1800032c3  mov     rax, [rcx]
0x1800032c6  lea     r9, [rsp+1B0h+var_178]
0x1800032cb  xorps   xmm0, xmm0
0x1800032ce  xor     edx, edx
0x1800032d0  movups  [rsp+1B0h+var_178], xmm0
0x1800032d5  mov     rax, [rax+70h]
0x1800032d9  lea     r8d, [rdx+1]
0x1800032dd  movups  [rsp+1B0h+var_168], xmm0
0x1800032e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e7  test    eax, eax
0x1800032e9  js      short loc_18000330A
0x1800032eb  mov     rcx, [rbx]
0x1800032ee  test    rcx, rcx
0x1800032f1  jz      loc_1800033E3
0x1800032f7  mov     qword ptr [rbx], 0
0x1800032fe  mov     rax, [rcx]
0x180003301  mov     rax, [rax+10h]
0x180003305  jmp     loc_1800033DE
0x18000330a  test    byte ptr [rdi+130h], 20h
0x180003311  jz      loc_1800033E7
0x180003317  xor     edi, edi
0x180003319  xor     esi, esi
0x18000331b  mov     rcx, [rbx]
0x18000331e  lea     r8, [rsp+1B0h+var_180]
0x180003323  mov     [rsp+1B0h+var_180], 0
0x18000332c  mov     edx, esi
0x18000332e  mov     rax, [rcx]
0x180003331  mov     rax, [rax+38h]
0x180003335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333a  test    eax, eax
0x18000333c  js      short loc_1800033A4
0x18000333e  xor     edx, edx; Val
0x180003340  lea     rcx, [rsp+1B0h+var_150]; void *
0x180003345  mov     r8d, 130h; Size
0x18000334b  call    memset_0
0x180003350  mov     rcx, [rsp+1B0h+var_180]
0x180003355  lea     rdx, [rsp+1B0h+var_150]
0x18000335a  mov     rax, [rcx]
0x18000335d  mov     rax, [rax+40h]
0x180003361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003366  test    eax, eax
0x180003368  js      short loc_18000337C
0x18000336a  cmp     [rbp+0B0h+var_50], 1414h
0x180003371  jnz     short loc_18000337C
0x180003373  cmp     [rbp+0B0h+var_4C], 8Ch
0x18000337a  jz      short loc_18000337E
0x18000337c  inc     edi
0x18000337e  mov     rcx, [rsp+1B0h+var_180]
0x180003383  test    rcx, rcx
0x180003386  jz      short loc_18000339D
0x180003388  mov     [rsp+1B0h+var_180], 0
0x180003391  mov     rax, [rcx]
0x180003394  mov     rax, [rax+10h]
0x180003398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339d  inc     esi
0x18000339f  jmp     loc_18000331B
0x1800033a4  mov     rcx, [rsp+1B0h+var_180]
0x1800033a9  test    rcx, rcx
0x1800033ac  jz      short loc_1800033C3
0x1800033ae  mov     [rsp+1B0h+var_180], 0
0x1800033b7  mov     rax, [rcx]
0x1800033ba  mov     rax, [rax+10h]
0x1800033be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c3  cmp     edi, 1
0x1800033c6  jnz     short loc_1800033E7
0x1800033c8  mov     rcx, [rbx]
0x1800033cb  test    rcx, rcx
0x1800033ce  jz      short loc_1800033E3
0x1800033d0  mov     qword ptr [rbx], 0
0x1800033d7  mov     rdx, [rcx]
0x1800033da  mov     rax, [rdx+10h]
0x1800033de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e3  mov     al, 1
0x1800033e5  jmp     short loc_180003404
0x1800033e7  mov     rcx, [rbx]
0x1800033ea  test    rcx, rcx
0x1800033ed  jz      short loc_180003402
0x1800033ef  mov     qword ptr [rbx], 0
0x1800033f6  mov     rax, [rcx]
0x1800033f9  mov     rax, [rax+10h]
0x1800033fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003402  xor     al, al
0x180003404  mov     rcx, [rbp+0B0h+var_20]
0x18000340b  xor     rcx, rsp; StackCookie
0x18000340e  call    __security_check_cookie
0x180003413  mov     rbx, [rsp+1B0h+arg_8]
0x18000341b  add     rsp, 1A0h
0x180003422  pop     rdi
0x180003423  pop     rsi
0x180003424  pop     rbp
0x180003425  retn
```
