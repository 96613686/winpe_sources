# AcquireLockSecurityObject

- ea: `0x180002a40`
- end: `0x180002b18`
- name: `AcquireLockSecurityObject`
- size: `216`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001dc0`
- `0x180002080`
- `0x180002200`
- `0x180002490`
- `0x180002650`
- `0x18000be70`

## callees

- `0x180002a40`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a80`

## pseudocode

```c
__int64 __fastcall AcquireLockSecurityObject(_DWORD *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)&g_pSecurity )
  {
    v3 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    *a1 = 1;
LABEL_6:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v3 = 5023;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_L(v2[2], 73, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 5023);
    goto LABEL_6;
  }
LABEL_7:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_L(v2[2], 74, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002a40  mov     [rsp+arg_8], rbx
0x180002a45  push    rsi
0x180002a46  sub     rsp, 20h
0x180002a4a  mov     rbx, rcx
0x180002a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a54  lea     rsi, WPP_GLOBAL_Control
0x180002a5b  cmp     rcx, rsi
0x180002a5e  jz      short loc_180002A66
0x180002a60  test    byte ptr [rcx+1Ch], 8
0x180002a64  jnz     short loc_180002ACA
0x180002a66  mov     rax, cs:g_pSecurity
0x180002a6d  mov     [rsp+28h+arg_0], rdi
0x180002a72  test    rax, rax
0x180002a75  jz      short loc_180002AEB
0x180002a77  xor     edi, edi
0x180002a79  lea     rcx, [rax+170h]; lpCriticalSection
0x180002a80  call    cs:__imp_EnterCriticalSection
0x180002a86  mov     dword ptr [rbx], 1
0x180002a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a93  cmp     rcx, rsi
0x180002a96  jz      short loc_180002A9E
0x180002a98  test    byte ptr [rcx+1Ch], 8
0x180002a9c  jnz     short loc_180002AB0
0x180002a9e  mov     rbx, [rsp+28h+arg_8]
0x180002aa3  mov     eax, edi
0x180002aa5  mov     rdi, [rsp+28h+arg_0]
0x180002aaa  add     rsp, 20h
0x180002aae  pop     rsi
0x180002aaf  retn
0x180002ab0  mov     rcx, [rcx+10h]
0x180002ab4  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002abb  mov     edx, 4Ah ; 'J'
0x180002ac0  mov     r9d, edi
0x180002ac3  call    WPP_SF_L
0x180002ac8  jmp     short loc_180002A9E
0x180002aca  mov     rcx, [rcx+10h]
0x180002ace  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002ad5  mov     edx, 48h ; 'H'
0x180002ada  call    WPP_SF_
0x180002adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ae6  jmp     loc_180002A66
0x180002aeb  mov     edi, 139Fh
0x180002af0  cmp     rcx, rsi
0x180002af3  jz      short loc_180002A9E
0x180002af5  test    byte ptr [rcx+1Ch], 4
0x180002af9  jz      short loc_180002A93
0x180002afb  mov     rcx, [rcx+10h]
0x180002aff  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002b06  mov     edx, 49h ; 'I'
0x180002b0b  mov     r9d, edi
0x180002b0e  call    WPP_SF_L
0x180002b13  jmp     loc_180002A8C
```
