# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800011ac`
- end: `0x180001252`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `166`
- prototype: ``
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x18000936c`
- `0x18000bfe0`
- `0x18000d344`
- `0x18000d6e4`
- `0x18000ddbc`
- `0x18000dec8`
- `0x18000e744`
- `0x18000e858`
- `0x18000ea88`
- `0x18000f170`
- `0x18000f228`
- `0x18000f3d0`
- `0x18000f5cc`
- `0x18000f648`
- `0x18000fc24`
- `0x18000fd38`
- `0x180010118`
- `0x1800109bc`
- `0x180012404`
- `0x180012774`
- `0x180012840`
- `0x180012e00`
- `0x180012fe0`
- `0x1800131ac`
- `0x180013ab4`
- `0x180014270`
- `0x1800145e0`
- `0x1800146e4`
- `0x1800148f0`

## callees

- `0x180001108`
- `0x1800011ac`
- `0x180001b90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 a6)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  const WCHAR *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &String2;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x1800011ac  sub     rsp, 88h
0x1800011b3  mov     rax, cs:__security_cookie
0x1800011ba  xor     rax, rsp
0x1800011bd  mov     [rsp+88h+var_18], rax
0x1800011c2  mov     rax, [rsp+88h+arg_28]
0x1800011ca  xor     r8d, r8d
0x1800011cd  mov     [rsp+88h+var_28], rax
0x1800011d2  mov     r9d, 4
0x1800011d8  mov     rax, [rsp+88h+arg_20]
0x1800011e0  mov     [rsp+88h+var_20], r9
0x1800011e5  mov     rcx, [rax]
0x1800011e8  test    rcx, rcx
0x1800011eb  jz      short loc_180001204
0x1800011ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011f1  inc     rax
0x1800011f4  cmp     [rcx+rax*2], r8w
0x1800011f9  jnz     short loc_1800011F1
0x1800011fb  lea     eax, ds:2[rax*2]
0x180001202  jmp     short loc_180001210
0x180001204  lea     rcx, String2
0x18000120b  mov     eax, 2
0x180001210  mov     [rsp+88h+var_30], eax
0x180001214  lea     rax, [rsp+88h+var_58]
0x180001219  mov     [rsp+88h+var_60], rax
0x18000121e  mov     [rsp+88h+var_68], r9d
0x180001223  xor     r9d, r9d
0x180001226  mov     [rsp+88h+var_38], rcx
0x18000122b  lea     rcx, dword_18004AE90
0x180001232  mov     [rsp+88h+var_2C], r8d
0x180001237  call    _tlgWriteTransfer_EventWriteTransfer
0x18000123c  mov     rcx, [rsp+88h+var_18]
0x180001241  xor     rcx, rsp; StackCookie
0x180001244  call    __security_check_cookie
0x180001249  add     rsp, 88h
0x180001250  retn
```
