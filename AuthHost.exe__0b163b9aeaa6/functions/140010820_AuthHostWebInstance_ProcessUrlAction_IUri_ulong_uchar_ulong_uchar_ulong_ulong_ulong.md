# AuthHostWebInstance::ProcessUrlAction(IUri *,ulong,uchar *,ulong,uchar *,ulong,ulong,ulong *)

- ea: `0x140010820`
- end: `0x1400108fa`
- name: `?ProcessUrlAction@AuthHostWebInstance@@UEAAJPEAUIUri@@KPEAEK1KKPEAK@Z`
- size: `218`
- prototype: `int(AuthHostWebInstance *__hidden this, struct IUri *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005760`

## callees

- `0x140010820`
- `0x140010900`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400108bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400108dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400108bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400108dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::ProcessUrlAction(
        AuthHostWebInstance *this,
        struct IUri *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int *a9)
{
  unsigned int v12; // edi
  const unsigned __int16 *v13; // rbx
  int v14; // ebx
  BSTR bstrString; // [rsp+68h] [rbp+10h] BYREF

  bstrString = 0;
  if ( a2 && a4 && (v12 = a5, a5 >= 4) )
  {
    v13 = 0;
    if ( ((int (__fastcall *)(struct IUri *, BSTR *))a2->lpVtbl->GetAbsoluteUri)(a2, &bstrString) >= 0 )
      v13 = bstrString;
    v14 = AuthHostWebInstance::ProcessUrlActionInternal(
            (AuthHostWebInstance *)((char *)this - 32),
            v13,
            a3,
            a4,
            v12,
            (IID *)a6,
            a7);
    if ( v14 >= 0 )
    {
      if ( a9 )
        *a9 = 0;
    }
    SysFreeString(bstrString);
    return (unsigned int)v14;
  }
  else
  {
    SysFreeString(0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140010820  mov     r11, rsp
0x140010823  mov     [r11+8], rbx
0x140010827  mov     [r11+18h], rbp
0x14001082b  push    rsi
0x14001082c  push    rdi
0x14001082d  push    r14
0x14001082f  sub     rsp, 40h
0x140010833  mov     rsi, r9
0x140010836  mov     ebp, r8d
0x140010839  mov     r9, rdx
0x14001083c  mov     r14, rcx
0x14001083f  mov     qword ptr [r11+10h], 0
0x140010847  test    rdx, rdx
0x14001084a  jz      loc_1400108DA
0x140010850  test    rsi, rsi
0x140010853  jz      loc_1400108DA
0x140010859  mov     edi, [rsp+58h+arg_20]
0x140010860  cmp     edi, 4
0x140010863  jb      short loc_1400108DA
0x140010865  xor     ebx, ebx
0x140010867  mov     rax, [rdx]
0x14001086a  lea     rdx, [r11+10h]
0x14001086e  mov     rcx, r9
0x140010871  mov     rax, [rax+38h]
0x140010875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001087a  test    eax, eax
0x14001087c  cmovns  rbx, [rsp+58h+bstrString]
0x140010882  lea     rcx, [r14-20h]; this
0x140010886  mov     eax, [rsp+58h+arg_30]
0x14001088d  mov     [rsp+58h+var_28], eax; unsigned int
0x140010891  mov     rax, [rsp+58h+arg_28]
0x140010899  mov     [rsp+58h+var_30], rax; unsigned __int8 *
0x14001089e  mov     [rsp+58h+var_38], edi; unsigned int
0x1400108a2  mov     r9, rsi; unsigned __int8 *
0x1400108a5  mov     r8d, ebp; unsigned int
0x1400108a8  mov     rdx, rbx; unsigned __int16 *
0x1400108ab  call    ?ProcessUrlActionInternal@AuthHostWebInstance@@AEAAJPEBGKPEAEK1K@Z; AuthHostWebInstance::ProcessUrlActionInternal(ushort const *,ulong,uchar *,ulong,uchar *,ulong)
0x1400108b0  mov     ebx, eax
0x1400108b2  test    eax, eax
0x1400108b4  jns     short loc_1400108C5
0x1400108b6  mov     rcx, [rsp+58h+bstrString]; bstrString
0x1400108bb  call    cs:__imp_SysFreeString
0x1400108c1  mov     eax, ebx
0x1400108c3  jmp     short loc_1400108E7
0x1400108c5  mov     rax, [rsp+58h+arg_40]
0x1400108cd  test    rax, rax
0x1400108d0  jz      short loc_1400108B6
0x1400108d2  mov     dword ptr [rax], 0
0x1400108d8  jmp     short loc_1400108B6
0x1400108da  xor     ecx, ecx; bstrString
0x1400108dc  call    cs:__imp_SysFreeString
0x1400108e2  mov     eax, 80070057h
0x1400108e7  mov     rbx, [rsp+58h+arg_0]
0x1400108ec  mov     rbp, [rsp+58h+arg_10]
0x1400108f1  add     rsp, 40h
0x1400108f5  pop     r14
0x1400108f7  pop     rdi
0x1400108f8  pop     rsi
0x1400108f9  retn
```
