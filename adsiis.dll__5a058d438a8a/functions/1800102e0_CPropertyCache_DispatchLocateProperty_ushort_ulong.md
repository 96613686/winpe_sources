# CPropertyCache::DispatchLocateProperty(ushort *,ulong *)

- ea: `0x1800102e0`
- end: `0x1800103b5`
- name: `?DispatchLocateProperty@CPropertyCache@@IEAAJPEAGPEAK@Z`
- size: `213`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010ec0`

## callees

- `0x18000c690`
- `0x18000ffe8`
- `0x18001009c`
- `0x1800102e0`
- `0x180010968`
- `0x18001bc84`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010380`
- `OLEAUT32!__imp_SysFreeString` at `0x180010397`
- `OLEAUT32!__imp_SysFreeString` at `0x180010380`
- `OLEAUT32!__imp_SysFreeString` at `0x180010397`

## pseudocode

```c
__int64 __fastcall CPropertyCache::DispatchLocateProperty(
        CCoreADsObject **this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  int Schema; // ebx
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  bstrString = 0;
  if ( a3 && a2 )
  {
    Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
    if ( Schema >= 0 )
    {
      Schema = CPropertyCache::DispatchFindProperty((CPropertyCache *)this, a2, a3);
      if ( Schema != -2147463155 )
        return (unsigned int)Schema;
      Schema = CCoreADsObject::get_CoreADsClass(this[2], &bstrString);
      if ( Schema >= 0 )
      {
        Schema = IIsSchema::ValidateProperty(this[9], bstrString, a2);
        if ( Schema >= 0 )
        {
          Schema = CPropertyCache::DispatchAddProperty((CPropertyCache *)this, a2, a3);
          if ( Schema >= 0 )
          {
            if ( bstrString )
              SysFreeString(bstrString);
            return (unsigned int)Schema;
          }
        }
      }
      if ( bstrString )
        SysFreeString(bstrString);
    }
    *a3 = -1;
    return (unsigned int)Schema;
  }
  return 2147614735LL;
}

```

## disassembly

```asm
0x1800102e0  push    rbx
0x1800102e2  push    rbp
0x1800102e3  push    rsi
0x1800102e4  push    r14
0x1800102e6  sub     rsp, 28h
0x1800102ea  mov     [rsp+48h+bstrString], 0
0x1800102f3  mov     r14, r8
0x1800102f6  mov     rbp, rdx
0x1800102f9  mov     rsi, rcx
0x1800102fc  test    r8, r8
0x1800102ff  jz      loc_1800103A6
0x180010305  test    rdx, rdx
0x180010308  jz      loc_1800103A6
0x18001030e  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010313  mov     ebx, eax
0x180010315  test    eax, eax
0x180010317  js      loc_18001039D
0x18001031d  mov     r8, r14; unsigned int *
0x180010320  mov     rdx, rbp; unsigned __int16 *
0x180010323  mov     rcx, rsi; this
0x180010326  call    ?DispatchFindProperty@CPropertyCache@@IEAAJPEAGPEAK@Z; CPropertyCache::DispatchFindProperty(ushort *,ulong *)
0x18001032b  mov     ebx, eax
0x18001032d  cmp     eax, 8000500Dh
0x180010332  jnz     short loc_180010386
0x180010334  mov     rcx, [rsi+10h]; this
0x180010338  lea     rdx, [rsp+48h+bstrString]; unsigned __int16 **
0x18001033d  call    ?get_CoreADsClass@CCoreADsObject@@QEAAJPEAPEAG@Z; CCoreADsObject::get_CoreADsClass(ushort * *)
0x180010342  mov     ebx, eax
0x180010344  test    eax, eax
0x180010346  js      short loc_18001038A
0x180010348  mov     rdx, [rsp+48h+bstrString]; unsigned __int16 *
0x18001034d  mov     r8, rbp; unsigned __int16 *
0x180010350  mov     rcx, [rsi+48h]; this
0x180010354  call    ?ValidateProperty@IIsSchema@@QEAAJPEBG0@Z; IIsSchema::ValidateProperty(ushort const *,ushort const *)
0x180010359  mov     ebx, eax
0x18001035b  test    eax, eax
0x18001035d  js      short loc_18001038A
0x18001035f  mov     r8, r14; unsigned int *
0x180010362  mov     rdx, rbp; unsigned __int16 *
0x180010365  mov     rcx, rsi; this
0x180010368  call    ?DispatchAddProperty@CPropertyCache@@IEAAJPEAGPEAK@Z; CPropertyCache::DispatchAddProperty(ushort *,ulong *)
0x18001036d  mov     ebx, eax
0x18001036f  test    eax, eax
0x180010371  js      short loc_18001038A
0x180010373  cmp     [rsp+48h+bstrString], 0
0x180010379  jz      short loc_180010386
0x18001037b  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180010380  call    cs:__imp_SysFreeString
0x180010386  mov     eax, ebx
0x180010388  jmp     short loc_1800103AB
0x18001038a  cmp     [rsp+48h+bstrString], 0
0x180010390  jz      short loc_18001039D
0x180010392  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180010397  call    cs:__imp_SysFreeString
0x18001039d  mov     dword ptr [r14], 0FFFFFFFFh
0x1800103a4  jmp     short loc_180010386
0x1800103a6  mov     eax, 8002000Fh
0x1800103ab  add     rsp, 28h
0x1800103af  pop     r14
0x1800103b1  pop     rsi
0x1800103b2  pop     rbp
0x1800103b3  pop     rbx
0x1800103b4  retn
```
