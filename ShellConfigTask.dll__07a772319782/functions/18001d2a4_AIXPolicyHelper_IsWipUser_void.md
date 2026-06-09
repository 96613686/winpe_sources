# AIXPolicyHelper::IsWipUser(void)

- ea: `0x18001d2a4`
- end: `0x18001d35f`
- name: `?IsWipUser@AIXPolicyHelper@@YA_NXZ`
- size: `187`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bf24`
- `0x18001c550`
- `0x18001e518`

## callees

- `0x18001d2a4`
- `0x18002062c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d2d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d2d5`

## string_xrefs

- `0x18001d308`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall AIXPolicyHelper::IsWipUser(AIXPolicyHelper *this)
{
  char v1; // bl
  int v2; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int16 v5; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v1 = 1;
  if ( CoCreateInstance(
         &GUID_3185a766_b338_11e4_a71e_12e3f512a338,
         0,
         1u,
         &GUID_e833feb2_c58a_45e4_8d93_08874744febb,
         &ppv) >= 0 )
  {
    v5 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, &v5);
    if ( v2 >= 0 )
    {
      if ( v5 == -1 )
      {
LABEL_6:
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v1;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x197,
        (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
        (const char *)(unsigned int)v2);
    }
    v1 = 0;
    goto LABEL_6;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x18001d2a4  push    rbx
0x18001d2a6  sub     rsp, 30h
0x18001d2aa  mov     [rsp+38h+arg_8], 0
0x18001d2b3  lea     rax, [rsp+38h+arg_8]
0x18001d2b8  mov     [rsp+38h+ppv], rax; int
0x18001d2bd  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x18001d2c4  mov     ebx, 1
0x18001d2c9  mov     r8d, ebx; dwClsContext
0x18001d2cc  xor     edx, edx; pUnkOuter
0x18001d2ce  lea     rcx, _GUID_3185a766_b338_11e4_a71e_12e3f512a338; rclsid
0x18001d2d5  call    cs:__imp_CoCreateInstance
0x18001d2db  test    eax, eax
0x18001d2dd  js      short loc_18001D340
0x18001d2df  xor     eax, eax
0x18001d2e1  mov     [rsp+38h+arg_0], ax
0x18001d2e6  mov     rcx, [rsp+38h+arg_8]
0x18001d2eb  mov     rax, [rcx]
0x18001d2ee  lea     rdx, [rsp+38h+arg_0]
0x18001d2f3  mov     rax, [rax+18h]
0x18001d2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2fc  mov     rcx, [rsp+38h]; this
0x18001d301  test    eax, eax
0x18001d303  jns     short loc_18001D31B
0x18001d305  mov     r9d, eax; char *
0x18001d308  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001d30f  mov     edx, 197h; void *
0x18001d314  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d319  jmp     short loc_18001D323
0x18001d31b  cmp     [rsp+38h+arg_0], 0FFFFh
0x18001d321  jz      short loc_18001D325
0x18001d323  xor     bl, bl
0x18001d325  mov     rcx, [rsp+38h+arg_8]
0x18001d32a  test    rcx, rcx
0x18001d32d  jz      short loc_18001D33C
0x18001d32f  mov     rdx, [rcx]
0x18001d332  mov     rax, [rdx+10h]
0x18001d336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d33b  nop
0x18001d33c  mov     al, bl
0x18001d33e  jmp     short loc_18001D359
0x18001d340  mov     rcx, [rsp+38h+arg_8]
0x18001d345  test    rcx, rcx
0x18001d348  jz      short loc_18001D357
0x18001d34a  mov     rax, [rcx]
0x18001d34d  mov     rax, [rax+10h]
0x18001d351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d356  nop
0x18001d357  xor     al, al
0x18001d359  add     rsp, 30h
0x18001d35d  pop     rbx
0x18001d35e  retn
```
