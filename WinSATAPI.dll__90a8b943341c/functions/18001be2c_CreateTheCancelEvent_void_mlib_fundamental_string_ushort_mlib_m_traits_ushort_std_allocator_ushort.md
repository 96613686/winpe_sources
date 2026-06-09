# CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001be2c`
- end: `0x18001beca`
- name: `?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `158`
- prototype: `signed int __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cc8c`
- `0x180021070`

## callees

- `0x18001be2c`
- `0x18001c09c`
- `0x18001c0f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001be8e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001be8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bea2`

## pseudocode

```c
signed int __fastcall CreateTheCancelEvent(_QWORD *a1, __int64 a2)
{
  signed int result; // eax
  HANDLE v5; // rax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF

  if ( mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(a2) )
    return -2147024888;
  *(&EventAttributes.nLength + 1) = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 1;
  result = SetAdminRights(&EventAttributes);
  if ( result >= 0 )
  {
    v5 = CreateEventW(&EventAttributes, 0, 0, *(LPCWSTR *)(*(_QWORD *)a2 + 24LL));
    *a1 = v5;
    if ( v5 )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001be2c  mov     [rsp+arg_0], rbx
0x18001be31  push    rdi
0x18001be32  sub     rsp, 40h
0x18001be36  mov     rdi, rcx
0x18001be39  mov     rbx, rdx
0x18001be3c  mov     rcx, rdx
0x18001be3f  call    ?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)
0x18001be44  test    eax, eax
0x18001be46  jz      short loc_18001BE4F
0x18001be48  mov     eax, 80070008h
0x18001be4d  jmp     short loc_18001BEBE
0x18001be4f  and     dword ptr [rsp+48h+EventAttributes+4], 0
0x18001be54  lea     rcx, [rsp+48h+EventAttributes]
0x18001be59  and     dword ptr [rsp+48h+EventAttributes+14h], 0
0x18001be5e  and     [rsp+48h+EventAttributes.lpSecurityDescriptor], 0
0x18001be64  mov     [rsp+48h+EventAttributes.nLength], 18h
0x18001be6c  mov     [rsp+48h+EventAttributes.bInheritHandle], 1
0x18001be74  call    SetAdminRights
0x18001be79  test    eax, eax
0x18001be7b  js      short loc_18001BEBE
0x18001be7d  mov     r9, [rbx]
0x18001be80  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x18001be85  xor     r8d, r8d; bInitialState
0x18001be88  xor     edx, edx; bManualReset
0x18001be8a  mov     r9, [r9+18h]; lpName
0x18001be8e  call    cs:__imp_CreateEventW
0x18001be95  nop     dword ptr [rax+rax+00h]
0x18001be9a  mov     [rdi], rax
0x18001be9d  test    rax, rax
0x18001bea0  jnz     short loc_18001BEBC
0x18001bea2  call    cs:__imp_GetLastError
0x18001bea9  nop     dword ptr [rax+rax+00h]
0x18001beae  test    eax, eax
0x18001beb0  jle     short loc_18001BEBE
0x18001beb2  movzx   eax, ax
0x18001beb5  or      eax, 80070000h
0x18001beba  jmp     short loc_18001BEBE
0x18001bebc  xor     eax, eax
0x18001bebe  mov     rbx, [rsp+48h+arg_0]
0x18001bec3  add     rsp, 40h
0x18001bec7  pop     rdi
0x18001bec8  retn
```
