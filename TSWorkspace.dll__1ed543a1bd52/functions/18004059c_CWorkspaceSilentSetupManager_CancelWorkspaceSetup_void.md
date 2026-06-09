# CWorkspaceSilentSetupManager::CancelWorkspaceSetup(void)

- ea: `0x18004059c`
- end: `0x1800406cc`
- name: `?CancelWorkspaceSetup@CWorkspaceSilentSetupManager@@QEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(CWorkspaceSilentSetupManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180025690`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18004059c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004066e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004066e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406ab`
- `USER32!PostThreadMessageW` at `0x18004064c`
- `USER32!PostThreadMessageW` at `0x18004064c`

## pseudocode

```c
signed int __fastcall CWorkspaceSilentSetupManager::CancelWorkspaceSetup(CWorkspaceSilentSetupManager *this)
{
  PVOID *v2; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD v4; // ecx
  unsigned int v5; // eax
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
      CurrentThreadActivityIdPrefix);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = *((_DWORD *)this + 5);
  if ( v4 )
  {
    if ( PostThreadMessageW(v4, 0x80CFu, 0, 0) )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids, v9, v8);
      }
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
        v5,
        -2147024809);
    }
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18004059c  mov     [rsp+arg_0], rbx
0x1800405a1  push    rdi
0x1800405a2  sub     rsp, 30h
0x1800405a6  mov     rbx, rcx
0x1800405a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800405b0  lea     rdi, WPP_GLOBAL_Control
0x1800405b7  cmp     rax, rdi
0x1800405ba  jz      short loc_1800405F3
0x1800405bc  test    byte ptr [rax+1Ch], 1
0x1800405c0  jz      short loc_1800405F3
0x1800405c2  cmp     byte ptr [rax+19h], 4
0x1800405c6  jb      short loc_1800405F3
0x1800405c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800405cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800405d4  lea     r8, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x1800405db  mov     edx, 13h
0x1800405e0  mov     r9d, eax
0x1800405e3  mov     rcx, [rcx+10h]
0x1800405e7  call    WPP_SF_D
0x1800405ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800405f3  mov     ecx, [rbx+14h]; idThread
0x1800405f6  test    ecx, ecx
0x1800405f8  jnz     short loc_180040641
0x1800405fa  cmp     rax, rdi
0x1800405fd  jz      short loc_180040637
0x1800405ff  test    byte ptr [rax+1Ch], 8
0x180040603  jz      short loc_180040637
0x180040605  cmp     byte ptr [rax+19h], 2
0x180040609  jb      short loc_180040637
0x18004060b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040610  mov     rcx, cs:WPP_GLOBAL_Control
0x180040617  lea     r8, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x18004061e  mov     edx, 14h
0x180040623  mov     [rsp+38h+var_18], 80070057h
0x18004062b  mov     r9d, eax
0x18004062e  mov     rcx, [rcx+10h]
0x180040632  call    WPP_SF_Dd
0x180040637  mov     eax, 80070057h
0x18004063c  jmp     loc_1800406C1
0x180040641  xor     r9d, r9d; lParam
0x180040644  xor     r8d, r8d; wParam
0x180040647  mov     edx, 80CFh; Msg
0x18004064c  call    cs:__imp_PostThreadMessageW
0x180040652  test    eax, eax
0x180040654  jnz     short loc_1800406BF
0x180040656  mov     rax, cs:WPP_GLOBAL_Control
0x18004065d  cmp     rax, rdi
0x180040660  jz      short loc_1800406AB
0x180040662  test    byte ptr [rax+1Ch], 8
0x180040666  jz      short loc_1800406AB
0x180040668  cmp     byte ptr [rax+19h], 2
0x18004066c  jb      short loc_1800406AB
0x18004066e  call    cs:__imp_GetLastError
0x180040674  mov     ebx, eax
0x180040676  test    eax, eax
0x180040678  jle     short loc_180040683
0x18004067a  movzx   ebx, ax
0x18004067d  or      ebx, 80070000h
0x180040683  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040688  mov     rcx, cs:WPP_GLOBAL_Control
0x18004068f  lea     r8, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x180040696  mov     edx, 15h
0x18004069b  mov     [rsp+38h+var_18], ebx
0x18004069f  mov     r9d, eax
0x1800406a2  mov     rcx, [rcx+10h]
0x1800406a6  call    WPP_SF_Dd
0x1800406ab  call    cs:__imp_GetLastError
0x1800406b1  test    eax, eax
0x1800406b3  jle     short loc_1800406C1
0x1800406b5  movzx   eax, ax
0x1800406b8  or      eax, 80070000h
0x1800406bd  jmp     short loc_1800406C1
0x1800406bf  xor     eax, eax
0x1800406c1  mov     rbx, [rsp+38h+arg_0]
0x1800406c6  add     rsp, 30h
0x1800406ca  pop     rdi
0x1800406cb  retn
```
