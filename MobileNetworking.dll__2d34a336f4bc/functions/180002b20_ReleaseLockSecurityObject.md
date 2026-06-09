# ReleaseLockSecurityObject

- ea: `0x180002b20`
- end: `0x180002bba`
- name: `ReleaseLockSecurityObject`
- size: `154`
- prototype: `void __fastcall(_DWORD *)`
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

- `0x180002b20`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b59`

## pseudocode

```c
void __fastcall ReleaseLockSecurityObject(_DWORD *a1)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *a1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v2 = (PVOID *)WPP_GLOBAL_Control;
    *a1 = 0;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_L(v2[2], 76, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_0], rbx
0x180002b25  push    rdi
0x180002b26  sub     rsp, 20h
0x180002b2a  mov     rbx, rcx
0x180002b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b34  lea     rdi, WPP_GLOBAL_Control
0x180002b3b  cmp     rcx, rdi
0x180002b3e  jz      short loc_180002B46
0x180002b40  test    byte ptr [rcx+1Ch], 8
0x180002b44  jnz     short loc_180002B82
0x180002b46  cmp     dword ptr [rbx], 0
0x180002b49  jz      short loc_180002B6C
0x180002b4b  mov     rcx, cs:g_pSecurity
0x180002b52  add     rcx, 170h; lpCriticalSection
0x180002b59  call    cs:__imp_LeaveCriticalSection
0x180002b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b66  mov     dword ptr [rbx], 0
0x180002b6c  cmp     rcx, rdi
0x180002b6f  jz      short loc_180002B77
0x180002b71  test    byte ptr [rcx+1Ch], 8
0x180002b75  jnz     short loc_180002BA0
0x180002b77  mov     rbx, [rsp+28h+arg_0]
0x180002b7c  add     rsp, 20h
0x180002b80  pop     rdi
0x180002b81  retn
0x180002b82  mov     rcx, [rcx+10h]
0x180002b86  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002b8d  mov     edx, 4Bh ; 'K'
0x180002b92  call    WPP_SF_
0x180002b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b9e  jmp     short loc_180002B46
0x180002ba0  mov     rcx, [rcx+10h]
0x180002ba4  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002bab  mov     edx, 4Ch ; 'L'
0x180002bb0  xor     r9d, r9d
0x180002bb3  call    WPP_SF_L
0x180002bb8  jmp     short loc_180002B77
```
