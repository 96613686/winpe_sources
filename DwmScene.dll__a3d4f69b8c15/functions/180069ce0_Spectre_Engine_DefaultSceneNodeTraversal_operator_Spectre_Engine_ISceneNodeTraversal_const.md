# Spectre::Engine::DefaultSceneNodeTraversal::operator==(Spectre::Engine::ISceneNodeTraversal const &)

- ea: `0x180069ce0`
- end: `0x180069d27`
- name: `??8DefaultSceneNodeTraversal@Engine@Spectre@@UEBA_NAEBVISceneNodeTraversal@12@@Z`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180069ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180069d0c`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180069d0c`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180069cf2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180069cfe`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180069cf2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180069cfe`

## pseudocode

```c
bool __fastcall Spectre::Engine::DefaultSceneNodeTraversal::operator==(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  bool result; // al

  result = 1;
  if ( a1 != a2 )
  {
    v3 = __RTtypeid(a1);
    v4 = __RTtypeid(a2);
    if ( (unsigned int)__std_type_info_compare(v3 + 8, v4 + 8) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180069ce0  mov     [rsp+arg_0], rbx
0x180069ce5  push    rdi
0x180069ce6  sub     rsp, 20h
0x180069cea  mov     rdi, rdx
0x180069ced  cmp     rcx, rdx
0x180069cf0  jz      short loc_180069D1A
0x180069cf2  call    cs:__imp___RTtypeid
0x180069cf8  mov     rcx, rdi
0x180069cfb  mov     rbx, rax
0x180069cfe  call    cs:__imp___RTtypeid
0x180069d04  lea     rcx, [rbx+8]
0x180069d08  lea     rdx, [rax+8]
0x180069d0c  call    cs:__imp___std_type_info_compare
0x180069d12  test    eax, eax
0x180069d14  jz      short loc_180069D1A
0x180069d16  xor     al, al
0x180069d18  jmp     short loc_180069D1C
0x180069d1a  mov     al, 1
0x180069d1c  mov     rbx, [rsp+28h+arg_0]
0x180069d21  add     rsp, 20h
0x180069d25  pop     rdi
0x180069d26  retn
```
