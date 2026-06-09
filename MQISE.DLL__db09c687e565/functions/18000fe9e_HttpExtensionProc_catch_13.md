# HttpExtensionProc$catch$13

- ea: `0x18000fe9e`
- end: `0x18000ff4c`
- name: `HttpExtensionProc$catch$13`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800096b8`
- `0x18000dd2c`
- `0x18000fe9e`
- `0x180011010`

## import_xrefs

- `ADVAPI32!GetUserNameW` at `0x18000feca`
- `ADVAPI32!GetUserNameW` at `0x18000feca`

## pseudocode

```c
_BOOL8 __fastcall HttpExtensionProc_catch_13(__int64 a1, __int64 a2)
{
  char v3; // al
  int v4; // edx
  int v5; // r8d

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) = 1000;
    if ( GetUserNameW((LPWSTR)(a2 + 304), (LPDWORD)(a2 + 48)) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 80) + 16LL))(*(_QWORD *)(a2 + 80));
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 12), v4, v5, a2 + 304, v3);
      }
    }
  }
  return (unsigned int)SendResponse(*(_QWORD *)(a2 + 64), (__int64)"401 Unauthorized", 0) != 0;
}

```

## disassembly

```asm
0x18000fe9e  mov     [rsp+arg_8], rdx
0x18000fea3  push    rbp
0x18000fea4  sub     rsp, 30h
0x18000fea8  mov     rbp, rdx
0x18000feab  mov     rax, cs:WPP_GLOBAL_Control
0x18000feb2  test    byte ptr [rax+6Ch], 1
0x18000feb6  jz      short loc_18000FF18
0x18000feb8  mov     dword ptr [rbp+30h], 3E8h
0x18000febf  lea     rdx, [rbp+30h]; pcbBuffer
0x18000fec3  lea     rcx, [rbp+130h]; lpBuffer
0x18000feca  call    cs:__imp_GetUserNameW
0x18000fed0  test    eax, eax
0x18000fed2  jz      short loc_18000FF18
0x18000fed4  lea     rcx, WPP_GLOBAL_Control
0x18000fedb  mov     rax, cs:WPP_GLOBAL_Control
0x18000fee2  cmp     rax, rcx
0x18000fee5  jz      short loc_18000FF18
0x18000fee7  test    byte ptr [rax+6Ch], 1
0x18000feeb  jz      short loc_18000FF18
0x18000feed  mov     rcx, [rbp+50h]
0x18000fef1  mov     rax, [rcx]
0x18000fef4  mov     rax, [rax+10h]
0x18000fef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fefd  mov     [rsp+38h+var_18], eax
0x18000ff01  lea     r9, [rbp+130h]
0x18000ff08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff0f  mov     rcx, [rcx+60h]
0x18000ff13  call    WPP_SF_SD
0x18000ff18  xor     r8d, r8d
0x18000ff1b  lea     rdx, a401Unauthorize; "401 Unauthorized"
0x18000ff22  mov     rcx, [rbp+40h]
0x18000ff26  call    SendResponse
0x18000ff2b  test    eax, eax
0x18000ff2d  jnz     short loc_18000FF3B
0x18000ff2f  mov     rax, 0
0x18000ff39  jmp     short loc_18000FF45
0x18000ff3b  mov     rax, 1
0x18000ff45  add     rsp, 30h
0x18000ff49  pop     rbp
0x18000ff4a  retn
```
