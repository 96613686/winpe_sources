# CGenerate::Generate(IWbemServices *,ushort const *,ushort const *,int)

- ea: `0x14000ab90`
- end: `0x14000ac41`
- name: `?Generate@CGenerate@@QEAAJPEAUIWbemServices@@PEBG1H@Z`
- size: `177`
- prototype: `__int64 __fastcall(unsigned __int16 **this, struct IWbemServices *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140007c10`

## callees

- `0x1400097d0`
- `0x14000ab90`
- `0x14000acd8`

## pseudocode

```c
__int64 __fastcall CGenerate::Generate(
        unsigned __int16 **this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int64 v7; // rax
  __int64 result; // rax
  unsigned __int16 *v9; // [rsp+20h] [rbp-18h] BYREF
  const unsigned __int16 *v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = a4;
  try
  {
    v9 = L"select * from meta_class where __this isa \"Win32_PerfRawData\"";
    v7 = *((unsigned int *)this + 20);
    if ( a5 )
    {
      __String::SetStringCopy(&(&this[4 * v7 + 1])[v7], &v10);
      __String::SetStringCopy(
        &(&this[4 * *((unsigned int *)this + 20) + 2])[*((unsigned int *)this + 20)],
        (const unsigned __int16 **)&v9);
      result = CObjectGlobal::GenerateObjects(
                 (CObjectGlobal *)&this[5 * *((unsigned int *)this + 20)],
                 a2,
                 L"select * from meta_class where __this isa \"Win32_PerfRawData\"",
                 a5);
      ++*((_DWORD *)this + 20);
    }
    else
    {
      result = CObjectGlobal::GenerateObjects(
                 (CObjectGlobal *)&this[5 * (unsigned int)(v7 - 1)],
                 a2,
                 L"select * from meta_class where __this isa \"Win32_PerfRawData\"",
                 0);
    }
  }
  catch ( ... )
  {
    a5 = -2147467259;
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000ab90  mov     r11, rsp
0x14000ab93  mov     [r11+8], rbx
0x14000ab97  mov     [r11+10h], rsi
0x14000ab9b  mov     [r11+20h], r9
0x14000ab9f  push    r14
0x14000aba1  sub     rsp, 30h
0x14000aba5  mov     rsi, rdx
0x14000aba8  mov     rbx, rcx
0x14000abab  lea     r14, aSelectFromMeta; "select * from meta_class where __this i"...
0x14000abb2  mov     [r11-18h], r14
0x14000abb6  mov     eax, [rcx+50h]
0x14000abb9  cmp     [rsp+38h+arg_20], 0
0x14000abbe  jz      short loc_14000AC14
0x14000abc0  lea     rdx, ds:1[rax*4]
0x14000abc8  add     rdx, rax
0x14000abcb  lea     rcx, [rcx+rdx*8]; unsigned __int16 **
0x14000abcf  lea     rdx, [r11+20h]; unsigned __int16 **
0x14000abd3  call    ?SetStringCopy@__String@@SAXAEAPEAGAEAPEBG@Z; __String::SetStringCopy(ushort * &,ushort const * &)
0x14000abd8  mov     eax, [rbx+50h]
0x14000abdb  lea     rcx, ds:2[rax*4]
0x14000abe3  add     rcx, rax
0x14000abe6  lea     rcx, [rbx+rcx*8]; unsigned __int16 **
0x14000abea  lea     rdx, [rsp+38h+var_18]; unsigned __int16 **
0x14000abef  call    ?SetStringCopy@__String@@SAXAEAPEAGAEAPEBG@Z; __String::SetStringCopy(ushort * &,ushort const * &)
0x14000abf4  mov     eax, [rbx+50h]
0x14000abf7  lea     rcx, [rax+rax*4]
0x14000abfb  lea     rcx, [rbx+rcx*8]; this
0x14000abff  mov     r9d, [rsp+38h+arg_20]; int
0x14000ac04  mov     r8, r14; unsigned __int16 *
0x14000ac07  mov     rdx, rsi; struct IWbemServices *
0x14000ac0a  call    ?GenerateObjects@CObjectGlobal@@QEAAJPEAUIWbemServices@@PEBGH@Z; CObjectGlobal::GenerateObjects(IWbemServices *,ushort const *,int)
0x14000ac0f  inc     dword ptr [rbx+50h]
0x14000ac12  jmp     short loc_14000AC2A
0x14000ac14  dec     eax
0x14000ac16  lea     rax, [rax+rax*4]
0x14000ac1a  lea     rcx, [rcx+rax*8]; this
0x14000ac1e  xor     r9d, r9d; int
0x14000ac21  mov     r8, r14; unsigned __int16 *
0x14000ac24  call    ?GenerateObjects@CObjectGlobal@@QEAAJPEAUIWbemServices@@PEBGH@Z; CObjectGlobal::GenerateObjects(IWbemServices *,ushort const *,int)
0x14000ac29  nop
0x14000ac2a  jmp     short loc_14000AC30
0x14000ac2c  mov     eax, [rsp+38h+arg_20]
0x14000ac30  mov     rbx, [rsp+38h+arg_0]
0x14000ac35  mov     rsi, [rsp+38h+arg_8]
0x14000ac3a  add     rsp, 30h
0x14000ac3e  pop     r14
0x14000ac40  retn
```
