# CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)

- ea: `0x1800148a0`
- end: `0x18001498b`
- name: `?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z`
- size: `235`
- prototype: `int(CCoreADsObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000204c`
- `0x180002d98`
- `0x18000549c`
- `0x1800084a8`
- `0x180009a44`
- `0x180009d90`
- `0x18000a0a8`

## callees

- `0x180012d2c`
- `0x180012e6c`
- `0x1800148a0`
- `0x18001beb8`
- `0x18001d6c0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800148f9`
- `ole32!StringFromGUID2` at `0x1800148f9`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::InitializeCoreObject(
        unsigned __int16 **this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        const unsigned __int16 *a5,
        const struct _GUID *rguid,
        unsigned int a7)
{
  int v11; // edx
  OLECHAR sz[264]; // [rsp+20h] [rbp-258h] BYREF

  v11 = BuildADsPath(a2, a3, this + 3);
  if ( v11 >= 0 )
  {
    StringFromGUID2(rguid, sz, 256);
    v11 = ADsAllocString(sz, this + 6);
    if ( v11 >= 0 )
    {
      v11 = ADsAllocString(a2, this + 4);
      if ( v11 >= 0 )
      {
        v11 = ADsAllocString(a3, this + 2);
        if ( v11 >= 0 )
        {
          v11 = ADsAllocString(a4, this + 5);
          if ( v11 >= 0 )
          {
            v11 = BuildSchemaPath(this[3], a4, this + 7);
            if ( v11 >= 0 )
              *((_DWORD *)this + 2) = a7;
          }
        }
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800148a0  push    rbx
0x1800148a2  push    rbp
0x1800148a3  push    rsi
0x1800148a4  push    rdi
0x1800148a5  push    r14
0x1800148a7  push    r15
0x1800148a9  sub     rsp, 248h
0x1800148b0  mov     rax, cs:__security_cookie
0x1800148b7  xor     rax, rsp
0x1800148ba  mov     [rsp+278h+var_48], rax
0x1800148c2  mov     r15, [rsp+278h+rguid]
0x1800148ca  mov     rbp, r8
0x1800148cd  mov     rsi, rdx
0x1800148d0  lea     r8, [rcx+18h]; unsigned __int16 **
0x1800148d4  mov     rbx, rcx
0x1800148d7  mov     rdx, rbp; wchar_t *
0x1800148da  mov     rcx, rsi; Source
0x1800148dd  mov     rdi, r9
0x1800148e0  call    ?BuildADsPath@@YAJPEBG0PEAPEAG@Z; BuildADsPath(ushort const *,ushort const *,ushort * *)
0x1800148e5  mov     edx, eax
0x1800148e7  test    eax, eax
0x1800148e9  js      short loc_180014969
0x1800148eb  mov     r8d, 100h; cchMax
0x1800148f1  lea     rdx, [rsp+278h+sz]; lpsz
0x1800148f6  mov     rcx, r15; rguid
0x1800148f9  call    cs:__imp_StringFromGUID2
0x1800148ff  lea     rdx, [rbx+30h]
0x180014903  lea     rcx, [rsp+278h+sz]
0x180014908  call    ADsAllocString
0x18001490d  mov     edx, eax
0x18001490f  test    eax, eax
0x180014911  js      short loc_180014969
0x180014913  lea     rdx, [rbx+20h]
0x180014917  mov     rcx, rsi
0x18001491a  call    ADsAllocString
0x18001491f  mov     edx, eax
0x180014921  test    eax, eax
0x180014923  js      short loc_180014969
0x180014925  lea     rdx, [rbx+10h]
0x180014929  mov     rcx, rbp
0x18001492c  call    ADsAllocString
0x180014931  mov     edx, eax
0x180014933  test    eax, eax
0x180014935  js      short loc_180014969
0x180014937  lea     rdx, [rbx+28h]
0x18001493b  mov     rcx, rdi
0x18001493e  call    ADsAllocString
0x180014943  mov     edx, eax
0x180014945  test    eax, eax
0x180014947  js      short loc_180014969
0x180014949  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18001494d  lea     r8, [rbx+38h]; unsigned __int16 **
0x180014951  mov     rdx, rdi; Source
0x180014954  call    ?BuildSchemaPath@@YAJPEBG0PEAPEAG@Z; BuildSchemaPath(ushort const *,ushort const *,ushort * *)
0x180014959  mov     edx, eax
0x18001495b  test    eax, eax
0x18001495d  js      short loc_180014969
0x18001495f  mov     eax, [rsp+278h+arg_30]
0x180014966  mov     [rbx+8], eax
0x180014969  mov     eax, edx
0x18001496b  mov     rcx, [rsp+278h+var_48]
0x180014973  xor     rcx, rsp; StackCookie
0x180014976  call    __security_check_cookie
0x18001497b  add     rsp, 248h
0x180014982  pop     r15
0x180014984  pop     r14
0x180014986  pop     rdi
0x180014987  pop     rsi
0x180014988  pop     rbp
0x180014989  pop     rbx
0x18001498a  retn
```
