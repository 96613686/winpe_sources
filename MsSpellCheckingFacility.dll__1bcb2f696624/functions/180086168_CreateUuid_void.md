# CreateUuid(void)

- ea: `0x180086168`
- end: `0x180086201`
- name: `?CreateUuid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180059bc0`

## callees

- `0x18001ee7c`
- `0x180061320`
- `0x180062314`
- `0x180086168`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800861d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800861d2`
- `RPCRT4!UuidCreateSequential` at `0x1800861b1`
- `RPCRT4!UuidCreateSequential` at `0x1800861b1`

## pseudocode

```c
char **__fastcall CreateUuid(char **a1)
{
  RPC_STATUS v2; // eax
  UUID Uuid; // [rsp+28h] [rbp-240h] BYREF
  OLECHAR sz; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v6[526]; // [rsp+42h] [rbp-226h] BYREF

  sz = 0;
  memset_0(v6, 0, 0x206u);
  Uuid = 0;
  v2 = UuidCreateSequential(&Uuid);
  if ( !v2 || v2 == 1824 )
    StringFromGUID2(&Uuid, &sz, 260);
  std::wstring::wstring(a1, &sz);
  return a1;
}

```

## disassembly

```asm
0x180086168  push    rbx
0x18008616a  sub     rsp, 260h
0x180086171  mov     rax, cs:__security_cookie
0x180086178  xor     rax, rsp
0x18008617b  mov     [rsp+268h+var_18], rax
0x180086183  mov     qword ptr [rsp+268h+Uuid.Data1], rcx
0x180086188  mov     rbx, rcx
0x18008618b  xor     eax, eax
0x18008618d  lea     rcx, [rsp+268h+var_226]; void *
0x180086192  xor     edx, edx; Val
0x180086194  mov     [rsp+268h+sz], ax
0x180086199  mov     r8d, 206h; Size
0x18008619f  call    memset_0
0x1800861a4  xorps   xmm0, xmm0
0x1800861a7  lea     rcx, [rsp+268h+Uuid]; Uuid
0x1800861ac  movups  xmmword ptr [rsp+268h+Uuid.Data1], xmm0
0x1800861b1  call    cs:__imp_UuidCreateSequential
0x1800861b7  test    eax, eax
0x1800861b9  jz      short loc_1800861C2
0x1800861bb  cmp     eax, 720h
0x1800861c0  jnz     short loc_1800861D8
0x1800861c2  mov     r8d, 104h; cchMax
0x1800861c8  lea     rdx, [rsp+268h+sz]; lpsz
0x1800861cd  lea     rcx, [rsp+268h+Uuid]; rguid
0x1800861d2  call    cs:__imp_StringFromGUID2
0x1800861d8  lea     rdx, [rsp+268h+sz]
0x1800861dd  mov     rcx, rbx
0x1800861e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800861e5  mov     rax, rbx
0x1800861e8  mov     rcx, [rsp+268h+var_18]
0x1800861f0  xor     rcx, rsp; StackCookie
0x1800861f3  call    __security_check_cookie
0x1800861f8  add     rsp, 260h
0x1800861ff  pop     rbx
0x180086200  retn
```
