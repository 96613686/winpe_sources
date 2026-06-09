# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)

- ea: `0x18000e23c`
- end: `0x18000e34b`
- name: `?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z`
- size: `271`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006eec`
- `0x18000ba58`
- `0x18000c290`
- `0x18000e354`
- `0x18000e960`
- `0x18000ef74`
- `0x18000f300`
- `0x18000f718`
- `0x1800137f8`
- `0x180013e14`
- `0x180013f40`
- `0x1800141d0`
- `0x180014338`
- `0x1800147fc`
- `0x180014964`
- `0x180014d1c`
- `0x180016f64`
- `0x180017c7c`
- `0x180018270`
- `0x180019b1c`
- `0x180019cfc`
- `0x18001a024`
- `0x18001a1f4`
- `0x18001a79c`

## callees

- `0x18000e23c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000e31b`
- `ntoskrnl!ZwClose` at `0x18000e31b`
- `ntoskrnl!ZwOpenKey` at `0x18000e2fd`
- `ntoskrnl!ZwOpenKey` at `0x18000e2fd`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
        void *a1,
        __int64 a2,
        HANDLE *a3)
{
  NTSTATUS result; // eax
  __int64 v7; // rax
  unsigned int v8; // edx
  __int16 v9; // cx
  NTSTATUS v10; // ebx
  void *v11; // rdi
  __int128 v12; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+88h] [rbp+28h] BYREF

  if ( !a2 )
    return -1073741811;
  KeyHandle = 0;
  v12 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v7 = -1;
  *(&ObjectAttributes.Attributes + 1) = 0;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v8 = 2 * v7;
  if ( (unsigned int)(2 * v7) > 0xFFFF )
    v9 = -1;
  else
    v9 = 2 * v7;
  if ( (v8 > 0xFFFF ? 0xC0000000 : 0) == 0xC0000000 )
  {
    if ( v8 > 0xFFFF )
      return v8 > 0xFFFF ? 0xC0000095 : 0;
  }
  else
  {
    *((_QWORD *)&v12 + 1) = a2;
    WORD1(v12) = v9;
    LOWORD(v12) = v9;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v10 = result;
  if ( result >= 0 )
  {
    v11 = KeyHandle;
    if ( *a3 )
      ZwClose(*a3);
    *a3 = v11;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18000e23c  mov     [rsp-18h+arg_0], rbx
0x18000e241  mov     [rsp-18h+arg_10], rsi
0x18000e246  push    rbp
0x18000e247  push    rdi
0x18000e248  push    r14
0x18000e24a  mov     rbp, rsp
0x18000e24d  sub     rsp, 60h
0x18000e251  xor     r14d, r14d
0x18000e254  mov     rsi, r8
0x18000e257  mov     r9, rdx
0x18000e25a  mov     r10, rcx
0x18000e25d  test    rdx, rdx
0x18000e260  jnz     short loc_18000E26C
0x18000e262  mov     eax, 0C000000Dh
0x18000e267  jmp     loc_18000E32C
0x18000e26c  xorps   xmm0, xmm0
0x18000e26f  mov     [rbp+KeyHandle], r14
0x18000e273  movups  [rbp+var_40], xmm0
0x18000e277  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x18000e27b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e27f  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x18000e283  inc     rax
0x18000e286  cmp     [rdx+rax*2], r14w
0x18000e28b  jnz     short loc_18000E283
0x18000e28d  lea     rdx, [rax+rax]
0x18000e291  mov     ebx, 0FFFFh
0x18000e296  cmp     edx, ebx
0x18000e298  ja      short loc_18000E29F
0x18000e29a  movzx   ecx, dx
0x18000e29d  jmp     short loc_18000E2A1
0x18000e29f  mov     ecx, ebx
0x18000e2a1  cmp     ebx, edx
0x18000e2a3  mov     r11d, 0C0000000h
0x18000e2a9  sbb     r8d, r8d
0x18000e2ac  and     r8d, 0C0000095h
0x18000e2b3  mov     eax, r8d
0x18000e2b6  and     eax, r11d
0x18000e2b9  cmp     eax, r11d
0x18000e2bc  jz      loc_18000E342
0x18000e2c2  mov     qword ptr [rbp+var_40+8], r9
0x18000e2c6  mov     word ptr [rbp+var_40+2], cx
0x18000e2ca  mov     word ptr [rbp+var_40], cx
0x18000e2ce  lea     rax, [rbp+var_40]
0x18000e2d2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000e2d9  xorps   xmm0, xmm0
0x18000e2dc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000e2e0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000e2e4  mov     [rbp+ObjectAttributes.RootDirectory], r10
0x18000e2e8  mov     edx, 10000000h; DesiredAccess
0x18000e2ed  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18000e2f4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000e2f8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000e2fd  call    cs:__imp_ZwOpenKey
0x18000e304  nop     dword ptr [rax+rax+00h]
0x18000e309  mov     ebx, eax
0x18000e30b  test    eax, eax
0x18000e30d  js      short loc_18000E32C
0x18000e30f  mov     rcx, [rsi]; Handle
0x18000e312  mov     rdi, [rbp+KeyHandle]
0x18000e316  test    rcx, rcx
0x18000e319  jz      short loc_18000E327
0x18000e31b  call    cs:__imp_ZwClose
0x18000e322  nop     dword ptr [rax+rax+00h]
0x18000e327  mov     [rsi], rdi
0x18000e32a  mov     eax, ebx
0x18000e32c  lea     r11, [rsp+60h+var_s0]
0x18000e331  mov     rbx, [r11+20h]
0x18000e335  mov     rsi, [r11+30h]
0x18000e339  mov     rsp, r11
0x18000e33c  pop     r14
0x18000e33e  pop     rdi
0x18000e33f  pop     rbp
0x18000e340  retn
0x18000e342  cmp     edx, ebx
0x18000e344  jbe     short loc_18000E2CE
0x18000e346  mov     eax, r8d
0x18000e349  jmp     short loc_18000E32C
```
