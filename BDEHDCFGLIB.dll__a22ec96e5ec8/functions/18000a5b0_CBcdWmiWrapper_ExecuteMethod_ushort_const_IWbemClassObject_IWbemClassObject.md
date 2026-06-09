# CBcdWmiWrapper::ExecuteMethod(ushort const *,IWbemClassObject *,IWbemClassObject * *)

- ea: `0x18000a5b0`
- end: `0x18000a707`
- name: `?ExecuteMethod@CBcdWmiWrapper@@IEAAJPEBGPEAUIWbemClassObject@@PEAPEAU2@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CBcdWmiWrapper *this, const unsigned __int16 *, struct IWbemClassObject *, struct IWbemClassObject **)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a710`
- `0x18000b72c`
- `0x18000b9d0`
- `0x18000be90`
- `0x18000c144`
- `0x18000c4d0`
- `0x18000c820`

## callees

- `0x18000a5b0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a5f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180013b03`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180013b03`
- `OLEAUT32!__imp_VariantInit` at `0x18000a5ec`
- `OLEAUT32!__imp_VariantInit` at `0x18000a5ec`
- `OLEAUT32!__imp_VariantClear` at `0x18000a6ee`
- `OLEAUT32!__imp_VariantClear` at `0x180013b15`
- `OLEAUT32!__imp_VariantClear` at `0x18000a6ee`
- `OLEAUT32!__imp_VariantClear` at `0x180013b15`

## pseudocode

```c
__int64 __fastcall CBcdWmiWrapper::ExecuteMethod(
        CBcdWmiWrapper *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject *a3,
        struct IWbemClassObject **a4)
{
  OLECHAR *v8; // rdi
  int v9; // ebx
  _QWORD v11[2]; // [rsp+58h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-50h] BYREF

  v11[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = SysAllocString(a2);
  v11[1] = v8;
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR *, _QWORD, _QWORD, struct IWbemClassObject *, _QWORD *, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
           *((_QWORD *)this + 2),
           *((_QWORD *)this + 4),
           v8,
           0,
           0,
           a3,
           v11,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v11[0] + 32LL))(
             v11[0],
             L"ReturnValue",
             0,
             &pvarg,
             0,
             0);
      if ( v9 >= 0 )
      {
        if ( pvarg.vt == 11 )
        {
          if ( pvarg.iVal )
          {
            if ( a4 )
            {
              *a4 = (struct IWbemClassObject *)v11[0];
              v11[0] = 0;
            }
          }
          else
          {
            v9 = 1;
          }
        }
        else
        {
          v9 = -1063256037;
        }
      }
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v11[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
    v11[0] = 0;
  }
  if ( v8 )
    SysFreeString(v8);
  VariantClear(&pvarg);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a5b0  mov     r11, rsp
0x18000a5b3  push    rbx
0x18000a5b4  push    rsi
0x18000a5b5  push    rdi
0x18000a5b6  push    r12
0x18000a5b8  push    r14
0x18000a5ba  push    r15
0x18000a5bc  sub     rsp, 88h
0x18000a5c3  mov     rsi, r9
0x18000a5c6  mov     r15, r8
0x18000a5c9  mov     rbx, rdx
0x18000a5cc  mov     r14, rcx
0x18000a5cf  xor     r12d, r12d
0x18000a5d2  mov     [r11-58h], r12
0x18000a5d6  mov     [r11-60h], r12
0x18000a5da  xorps   xmm0, xmm0
0x18000a5dd  xor     eax, eax
0x18000a5df  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x18000a5e4  mov     [r11-40h], rax
0x18000a5e8  lea     rcx, [r11-50h]; pvarg
0x18000a5ec  call    cs:__imp_VariantInit
0x18000a5f2  mov     rcx, rbx; psz
0x18000a5f5  call    cs:__imp_SysAllocString
0x18000a5fb  mov     rdi, rax
0x18000a5fe  mov     [rsp+0B8h+var_58], rax
0x18000a603  test    rax, rax
0x18000a606  jnz     short loc_18000A616
0x18000a608  mov     ebx, 8007000Eh
0x18000a60d  mov     [rsp+0B8h+var_68], ebx
0x18000a611  jmp     loc_18000A6C0
0x18000a616  mov     rcx, [r14+10h]
0x18000a61a  mov     rax, [rcx]
0x18000a61d  mov     [rsp+0B8h+var_80], r12
0x18000a622  lea     rdx, [rsp+0B8h+var_60]
0x18000a627  mov     [rsp+0B8h+var_88], rdx
0x18000a62c  mov     [rsp+0B8h+var_90], r15
0x18000a631  mov     [rsp+0B8h+var_98], r12
0x18000a636  xor     r9d, r9d
0x18000a639  mov     r8, rdi
0x18000a63c  mov     rdx, [r14+20h]
0x18000a640  mov     rax, [rax+0C0h]
0x18000a647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a64c  mov     ebx, eax
0x18000a64e  mov     [rsp+0B8h+var_68], eax
0x18000a652  test    eax, eax
0x18000a654  js      short loc_18000A6C0
0x18000a656  mov     rcx, [rsp+0B8h+var_60]
0x18000a65b  mov     rax, [rcx]
0x18000a65e  mov     [rsp+0B8h+var_90], r12
0x18000a663  mov     [rsp+0B8h+var_98], r12
0x18000a668  lea     r9, [rsp+0B8h+pvarg]
0x18000a66d  xor     r8d, r8d
0x18000a670  lea     rdx, aReturnvalue; "ReturnValue"
0x18000a677  mov     rax, [rax+20h]
0x18000a67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a680  mov     ebx, eax
0x18000a682  mov     [rsp+0B8h+var_68], eax
0x18000a686  test    eax, eax
0x18000a688  js      short loc_18000A6C0
0x18000a68a  cmp     word ptr [rsp+0B8h+pvarg], 0Bh
0x18000a690  jz      short loc_18000A69C
0x18000a692  mov     ebx, 0C0A0001Bh
0x18000a697  jmp     loc_18000A60D
0x18000a69c  cmp     word ptr [rsp+0B8h+pvarg+8], r12w
0x18000a6a2  jnz     short loc_18000A6AE
0x18000a6a4  mov     ebx, 1
0x18000a6a9  jmp     loc_18000A60D
0x18000a6ae  test    rsi, rsi
0x18000a6b1  jz      short loc_18000A6C0
0x18000a6b3  mov     rax, [rsp+0B8h+var_60]
0x18000a6b8  mov     [rsi], rax
0x18000a6bb  mov     [rsp+0B8h+var_60], r12
0x18000a6c0  mov     rcx, [rsp+0B8h+var_60]
0x18000a6c5  test    rcx, rcx
0x18000a6c8  jz      short loc_18000A6DB
0x18000a6ca  mov     rax, [rcx]
0x18000a6cd  mov     rax, [rax+10h]
0x18000a6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d6  mov     [rsp+0B8h+var_60], r12
0x18000a6db  test    rdi, rdi
0x18000a6de  jz      short loc_18000A6E9
0x18000a6e0  mov     rcx, rdi; bstrString
0x18000a6e3  call    cs:__imp_SysFreeString
0x18000a6e9  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000a6ee  call    cs:__imp_VariantClear
0x18000a6f4  mov     eax, ebx
0x18000a6f6  add     rsp, 88h
0x18000a6fd  pop     r15
0x18000a6ff  pop     r14
0x18000a701  pop     r12
0x18000a703  pop     rdi
0x18000a704  pop     rsi
0x18000a705  pop     rbx
0x18000a706  retn
0x180013ad4  push    rbp
0x180013ad6  sub     rsp, 50h
0x180013ada  mov     rbp, rdx
0x180013add  mov     rcx, [rbp+58h]
0x180013ae1  test    rcx, rcx
0x180013ae4  jz      short loc_180013AFA
0x180013ae6  mov     rax, [rcx]
0x180013ae9  mov     rax, [rax+10h]
0x180013aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af2  mov     qword ptr [rbp+58h], 0
0x180013afa  mov     rcx, [rbp+60h]; bstrString
0x180013afe  test    rcx, rcx
0x180013b01  jz      short loc_180013B11
0x180013b03  call    cs:__imp_SysFreeString
0x180013b09  mov     qword ptr [rbp+60h], 0
0x180013b11  lea     rcx, [rbp+68h]; pvarg
0x180013b15  call    cs:__imp_VariantClear
0x180013b1b  nop
0x180013b1c  add     rsp, 50h
0x180013b20  pop     rbp
0x180013b21  retn
```
