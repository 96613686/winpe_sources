# NTUserCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x180010790`
- end: `0x180010827`
- name: `?AccessCheck@NTUserCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(NTUserCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000fc5c`
- `0x180010790`
- `0x180010be0`
- `0x180013658`

## pseudocode

```c
__int64 __fastcall NTUserCapabilityHandler::AccessCheck(
        NTUserCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *a7)
{
  char *v8; // rcx
  unsigned __int64 v9; // rdx
  char *v11; // rsi
  __int64 v12; // rbx
  NTUserCapabilityHandler *v13; // rcx

  v8 = (char *)this + 32;
  v9 = -1;
  *(_DWORD *)a7 = 1;
  do
    ++v9;
  while ( a3[v9] );
  if ( v9 > *((_QWORD *)v8 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, a3, a3);
  }
  else
  {
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v11 = v8;
    else
      v11 = *(char **)v8;
    v12 = 2 * v9;
    *((_QWORD *)v8 + 2) = v9;
    memmove_0(v11, a3, 2 * v9);
    *(_WORD *)&v11[v12] = 0;
  }
  if ( !gHandlingAccessChanged && NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(v13, a3) )
    *((_DWORD *)this + 6) = a5;
  return 0;
}

```

## disassembly

```asm
0x180010790  push    rbx
0x180010792  push    rbp
0x180010793  push    rsi
0x180010794  push    rdi
0x180010795  push    r14
0x180010797  sub     rsp, 20h
0x18001079b  mov     rax, [rsp+48h+arg_30]
0x1800107a3  mov     rbp, rcx
0x1800107a6  add     rcx, 20h ; ' '
0x1800107aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800107ae  mov     rdi, r8
0x1800107b1  xor     r14d, r14d
0x1800107b4  mov     dword ptr [rax], 1
0x1800107ba  inc     rdx
0x1800107bd  cmp     [r8+rdx*2], r14w
0x1800107c2  jnz     short loc_1800107BA
0x1800107c4  cmp     rdx, [rcx+18h]
0x1800107c8  ja      short loc_1800107F6
0x1800107ca  cmp     qword ptr [rcx+18h], 7
0x1800107cf  jbe     short loc_1800107D6
0x1800107d1  mov     rsi, [rcx]
0x1800107d4  jmp     short loc_1800107D9
0x1800107d6  mov     rsi, rcx
0x1800107d9  lea     rbx, [rdx+rdx]
0x1800107dd  mov     [rcx+10h], rdx
0x1800107e1  mov     r8, rbx; Size
0x1800107e4  mov     rdx, rdi; Src
0x1800107e7  mov     rcx, rsi; void *
0x1800107ea  call    memmove_0
0x1800107ef  mov     [rbx+rsi], r14w
0x1800107f4  jmp     short loc_1800107FE
0x1800107f6  mov     r9, rdi
0x1800107f9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800107fe  cmp     cs:?gHandlingAccessChanged@@3_NA, r14b; bool gHandlingAccessChanged
0x180010805  jnz     short loc_18001081A
0x180010807  mov     rdx, rdi; unsigned __int16 *
0x18001080a  call    ?IsCapabilityRelevantToNTUser@NTUserCapabilityHandler@@AEBA_NPEBG@Z; NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(ushort const *)
0x18001080f  test    al, al
0x180010811  jz      short loc_18001081A
0x180010813  mov     eax, [rsp+48h+arg_20]
0x180010817  mov     [rbp+18h], eax
0x18001081a  xor     eax, eax
0x18001081c  add     rsp, 20h
0x180010820  pop     r14
0x180010822  pop     rdi
0x180010823  pop     rsi
0x180010824  pop     rbp
0x180010825  pop     rbx
0x180010826  retn
```
