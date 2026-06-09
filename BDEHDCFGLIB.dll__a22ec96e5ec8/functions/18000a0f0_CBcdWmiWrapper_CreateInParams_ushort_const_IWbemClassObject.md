# CBcdWmiWrapper::CreateInParams(ushort const *,IWbemClassObject * *)

- ea: `0x18000a0f0`
- end: `0x18000a1b7`
- name: `?CreateInParams@CBcdWmiWrapper@@IEAAJPEBGPEAPEAUIWbemClassObject@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(CBcdWmiWrapper *this, const unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a710`
- `0x18000b72c`
- `0x18000b9d0`
- `0x18000be90`
- `0x18000c4d0`
- `0x18000c820`

## callees

- `0x18000a0f0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a119`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a119`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a19f`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a19f`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a7f`

## pseudocode

```c
__int64 __fastcall CBcdWmiWrapper::CreateInParams(
        CBcdWmiWrapper *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject **a3)
{
  OLECHAR *v5; // rbx
  int v6; // edi
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 3) + 152LL))(
           *((_QWORD *)this + 3),
           v5,
           0,
           &v8,
           0);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v8 + 120LL))(v8, 0, a3);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v5 )
    SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a0f0  mov     rax, rsp
0x18000a0f3  mov     [rax+8], rbx
0x18000a0f7  mov     [rax+10h], rsi
0x18000a0fb  push    rdi
0x18000a0fc  sub     rsp, 40h
0x18000a100  mov     rsi, r8
0x18000a103  mov     rdi, rcx
0x18000a106  mov     qword ptr [rax+20h], 0
0x18000a10e  mov     qword ptr [rax-18h], 0
0x18000a116  mov     rcx, rdx; psz
0x18000a119  call    cs:__imp_SysAllocString
0x18000a11f  mov     rbx, rax
0x18000a122  mov     [rsp+48h+var_18], rax
0x18000a127  test    rax, rax
0x18000a12a  jnz     short loc_18000A133
0x18000a12c  mov     edi, 8007000Eh
0x18000a131  jmp     short loc_18000A178
0x18000a133  mov     rcx, [rdi+18h]
0x18000a137  mov     rax, [rcx]
0x18000a13a  mov     [rsp+48h+var_28], 0
0x18000a143  lea     r9, [rsp+48h+arg_18]
0x18000a148  xor     r8d, r8d
0x18000a14b  mov     rdx, rbx
0x18000a14e  mov     rax, [rax+98h]
0x18000a155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a15a  mov     edi, eax
0x18000a15c  test    eax, eax
0x18000a15e  js      short loc_18000A178
0x18000a160  mov     rcx, [rsp+48h+arg_18]
0x18000a165  mov     rax, [rcx]
0x18000a168  mov     r8, rsi
0x18000a16b  xor     edx, edx
0x18000a16d  mov     rax, [rax+78h]
0x18000a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a176  mov     edi, eax
0x18000a178  mov     rcx, [rsp+48h+arg_18]
0x18000a17d  test    rcx, rcx
0x18000a180  jz      short loc_18000A197
0x18000a182  mov     rax, [rcx]
0x18000a185  mov     rax, [rax+10h]
0x18000a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18e  mov     [rsp+48h+arg_18], 0
0x18000a197  test    rbx, rbx
0x18000a19a  jz      short loc_18000A1A5
0x18000a19c  mov     rcx, rbx; bstrString
0x18000a19f  call    cs:__imp_SysFreeString
0x18000a1a5  mov     eax, edi
0x18000a1a7  mov     rbx, [rsp+48h+arg_0]
0x18000a1ac  mov     rsi, [rsp+48h+arg_8]
0x18000a1b1  add     rsp, 40h
0x18000a1b5  pop     rdi
0x18000a1b6  retn
0x180013a50  push    rbp
0x180013a52  sub     rsp, 30h
0x180013a56  mov     rbp, rdx
0x180013a59  mov     rcx, [rbp+68h]
0x180013a5d  test    rcx, rcx
0x180013a60  jz      short loc_180013A76
0x180013a62  mov     rax, [rcx]
0x180013a65  mov     rax, [rax+10h]
0x180013a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a6e  mov     qword ptr [rbp+68h], 0
0x180013a76  mov     rcx, [rbp+30h]; bstrString
0x180013a7a  test    rcx, rcx
0x180013a7d  jz      short loc_180013A8D
0x180013a7f  call    cs:__imp_SysFreeString
0x180013a85  mov     qword ptr [rbp+30h], 0
0x180013a8d  add     rsp, 30h
0x180013a91  pop     rbp
0x180013a92  retn
```
