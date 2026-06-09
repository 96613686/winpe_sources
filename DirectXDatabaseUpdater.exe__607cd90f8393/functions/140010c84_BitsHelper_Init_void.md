# BitsHelper::Init(void)

- ea: `0x140010c84`
- end: `0x140010ce1`
- name: `?Init@BitsHelper@@AEAAJXZ`
- size: `93`
- prototype: `__int64 __fastcall(BitsHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010ac0`
- `0x140010ce8`

## callees

- `0x14000a4bc`
- `0x140010c84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010cb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010cb0`

## string_xrefs

- `0x140010cc4`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BitsHelper::Init(LPVOID *this)
{
  HRESULT Instance; // eax
  unsigned int v2; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *this )
    return 0;
  *this = 0;
  Instance = CoCreateInstance(
               &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
               0,
               4u,
               &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
               this);
  v2 = Instance;
  if ( Instance >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x140010c84  push    rbx
0x140010c86  sub     rsp, 30h
0x140010c8a  cmp     qword ptr [rcx], 0
0x140010c8e  jnz     short loc_140010CD9
0x140010c90  mov     qword ptr [rcx], 0
0x140010c97  mov     qword ptr [rsp+38h+ppv], rcx; int
0x140010c9c  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x140010ca3  xor     edx, edx; pUnkOuter
0x140010ca5  lea     r8d, [rdx+4]; dwClsContext
0x140010ca9  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x140010cb0  call    cs:__imp_CoCreateInstance
0x140010cb6  mov     ebx, eax
0x140010cb8  test    eax, eax
0x140010cba  jns     short loc_140010CD9
0x140010cbc  mov     rcx, [rsp+38h]; this
0x140010cc1  mov     r9d, eax; char *
0x140010cc4  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010ccb  mov     edx, 37h ; '7'; void *
0x140010cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010cd5  mov     eax, ebx
0x140010cd7  jmp     short loc_140010CDB
0x140010cd9  xor     eax, eax
0x140010cdb  add     rsp, 30h
0x140010cdf  pop     rbx
0x140010ce0  retn
```
