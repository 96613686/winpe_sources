# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x1400066c4`
- end: `0x140006788`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `196`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, const struct _GUID *, const unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006690`
- `0x1400066b0`

## callees

- `0x1400066c4`
- `0x1400069fc`
- `0x14000c1f0`
- `0x140015a56`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // r14
  __int64 v11; // rsi
  int v12; // eax
  int v13; // ebx
  int v14; // r12d

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 5);
    if ( v11 && a4 == 1 )
    {
      v12 = ocslen(*a3);
      v13 = *((_DWORD *)this + 12);
      v14 = v12;
      while ( --v13 >= 0 )
      {
        if ( v14 == *(_DWORD *)(v11 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v13), *a3, 2LL * *(int *)(v11 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
             v10,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x1400066c4  push    rbx
0x1400066c6  push    rbp
0x1400066c7  push    rsi
0x1400066c8  push    rdi
0x1400066c9  push    r12
0x1400066cb  push    r14
0x1400066cd  push    r15
0x1400066cf  sub     rsp, 30h
0x1400066d3  cmp     qword ptr [rcx+18h], 0
0x1400066d8  mov     ebp, r9d
0x1400066db  mov     r15, r8
0x1400066de  mov     rdi, rcx
0x1400066e1  jz      short loc_1400066EE
0x1400066e3  cmp     qword ptr [rcx+28h], 0
0x1400066e8  jz      short loc_1400066EE
0x1400066ea  xor     eax, eax
0x1400066ec  jmp     short loc_1400066FA
0x1400066ee  mov     edx, [rsp+68h+lcid]; lcid
0x1400066f5  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1400066fa  mov     r14, [rdi+18h]
0x1400066fe  test    r14, r14
0x140006701  jz      short loc_140006779
0x140006703  mov     rsi, [rdi+28h]
0x140006707  test    rsi, rsi
0x14000670a  jz      short loc_14000675C
0x14000670c  cmp     ebp, 1
0x14000670f  jnz     short loc_14000675C
0x140006711  mov     rcx, [r15]; unsigned __int16 *
0x140006714  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x140006719  mov     ebx, [rdi+30h]
0x14000671c  mov     r12d, eax
0x14000671f  dec     ebx
0x140006721  test    ebx, ebx
0x140006723  js      short loc_14000675C
0x140006725  movsxd  rdi, ebx
0x140006728  add     rdi, rdi
0x14000672b  cmp     r12d, [rsi+rdi*8+8]
0x140006730  jnz     short loc_14000671F
0x140006732  movsxd  r8, dword ptr [rsi+rdi*8+8]
0x140006737  mov     rdx, [r15]; Buf2
0x14000673a  add     r8, r8; Size
0x14000673d  mov     rcx, [rsi+rdi*8]; Buf1
0x140006741  call    memcmp_0
0x140006746  test    eax, eax
0x140006748  jnz     short loc_14000671F
0x14000674a  mov     rax, [rsp+68h+arg_28]
0x140006752  mov     ecx, [rsi+rdi*8+0Ch]
0x140006756  mov     [rax], ecx
0x140006758  xor     eax, eax
0x14000675a  jmp     short loc_140006779
0x14000675c  mov     rax, [r14]
0x14000675f  mov     r8d, ebp
0x140006762  mov     r9, [rsp+68h+arg_28]
0x14000676a  mov     rdx, r15
0x14000676d  mov     rcx, r14
0x140006770  mov     rax, [rax+50h]
0x140006774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006779  add     rsp, 30h
0x14000677d  pop     r15
0x14000677f  pop     r14
0x140006781  pop     r12
0x140006783  pop     rdi
0x140006784  pop     rsi
0x140006785  pop     rbp
0x140006786  pop     rbx
0x140006787  retn
```
