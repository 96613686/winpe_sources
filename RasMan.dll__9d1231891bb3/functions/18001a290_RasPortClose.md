# RasPortClose

- ea: `0x18001a290`
- end: `0x18001a3f0`
- name: `RasPortClose`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180017040`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001a290`
- `0x180021000`
- `0x180021488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a2d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a2d9`

## pseudocode

```c
__int64 __fastcall RasPortClose(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  DWORD v3; // esi
  PVOID *v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  CurrentProcessId = GetCurrentProcessId();
  v3 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 114;
LABEL_28:
        WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  v7 = SubmitLocalRequest(2u, a1, v3, 1);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_24;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 116;
    goto LABEL_28;
  }
  return v5;
}

```

## disassembly

```asm
0x18001a290  push    rbx
0x18001a292  push    rsi
0x18001a293  push    rdi
0x18001a294  push    r14
0x18001a296  push    r15
0x18001a298  sub     rsp, 20h
0x18001a29c  mov     rdi, rcx
0x18001a29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2a6  lea     r14, WPP_GLOBAL_Control
0x18001a2ad  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a2b4  cmp     rcx, r14
0x18001a2b7  jz      short loc_18001A2D9
0x18001a2b9  test    byte ptr [rcx+1Ch], 40h
0x18001a2bd  jz      short loc_18001A2D9
0x18001a2bf  cmp     byte ptr [rcx+19h], 6
0x18001a2c3  jb      short loc_18001A2D9
0x18001a2c5  mov     rcx, [rcx+10h]
0x18001a2c9  mov     edx, 6Fh ; 'o'
0x18001a2ce  mov     r9, rdi
0x18001a2d1  mov     r8, r15
0x18001a2d4  call    WPP_SF_q
0x18001a2d9  call    cs:__imp_GetCurrentProcessId
0x18001a2df  mov     esi, eax
0x18001a2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2e8  cmp     rcx, r14
0x18001a2eb  jz      short loc_18001A30D
0x18001a2ed  test    byte ptr [rcx+1Ch], 40h
0x18001a2f1  jz      short loc_18001A30D
0x18001a2f3  cmp     byte ptr [rcx+19h], 5
0x18001a2f7  jb      short loc_18001A30D
0x18001a2f9  mov     rcx, [rcx+10h]
0x18001a2fd  mov     edx, 70h ; 'p'
0x18001a302  mov     r9d, eax
0x18001a305  mov     r8, r15
0x18001a308  call    WPP_SF_d
0x18001a30d  mov     rcx, rdi
0x18001a310  call    ValidatePortHandle
0x18001a315  test    eax, eax
0x18001a317  jnz     short loc_18001A371
0x18001a319  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a320  mov     edi, 259h
0x18001a325  cmp     rcx, r14
0x18001a328  jz      loc_18001A3E2
0x18001a32e  test    byte ptr [rcx+1Ch], 40h
0x18001a332  jz      short loc_18001A355
0x18001a334  lea     ebx, [rax+2]
0x18001a337  cmp     [rcx+19h], bl
0x18001a33a  jb      short loc_18001A355
0x18001a33c  mov     rcx, [rcx+10h]
0x18001a340  lea     edx, [rax+71h]
0x18001a343  mov     r9d, edi
0x18001a346  mov     r8, r15
0x18001a349  call    WPP_SF_d
0x18001a34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a355  cmp     rcx, r14
0x18001a358  jz      loc_18001A3E2
0x18001a35e  test    byte ptr [rcx+1Ch], 40h
0x18001a362  jz      short loc_18001A3E2
0x18001a364  cmp     byte ptr [rcx+19h], 6
0x18001a368  jb      short loc_18001A3E2
0x18001a36a  mov     edx, 72h ; 'r'
0x18001a36f  jmp     short loc_18001A3D3
0x18001a371  mov     ebx, 2
0x18001a376  mov     r8d, esi
0x18001a379  mov     rdx, rdi
0x18001a37c  mov     ecx, ebx
0x18001a37e  lea     r9d, [rbx-1]
0x18001a382  call    SubmitLocalRequest
0x18001a387  mov     edi, eax
0x18001a389  test    eax, eax
0x18001a38b  jz      short loc_18001A3B6
0x18001a38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a394  cmp     rcx, r14
0x18001a397  jz      short loc_18001A3E2
0x18001a399  test    byte ptr [rcx+1Ch], 40h
0x18001a39d  jz      short loc_18001A3BD
0x18001a39f  cmp     [rcx+19h], bl
0x18001a3a2  jb      short loc_18001A3BD
0x18001a3a4  mov     rcx, [rcx+10h]
0x18001a3a8  lea     edx, [rbx+71h]
0x18001a3ab  mov     r9d, eax
0x18001a3ae  mov     r8, r15
0x18001a3b1  call    WPP_SF_d
0x18001a3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3bd  cmp     rcx, r14
0x18001a3c0  jz      short loc_18001A3E2
0x18001a3c2  test    byte ptr [rcx+1Ch], 40h
0x18001a3c6  jz      short loc_18001A3E2
0x18001a3c8  cmp     byte ptr [rcx+19h], 6
0x18001a3cc  jb      short loc_18001A3E2
0x18001a3ce  mov     edx, 74h ; 't'
0x18001a3d3  mov     rcx, [rcx+10h]
0x18001a3d7  mov     r9d, edi
0x18001a3da  mov     r8, r15
0x18001a3dd  call    WPP_SF_d
0x18001a3e2  mov     eax, edi
0x18001a3e4  add     rsp, 20h
0x18001a3e8  pop     r15
0x18001a3ea  pop     r14
0x18001a3ec  pop     rdi
0x18001a3ed  pop     rsi
0x18001a3ee  pop     rbx
0x18001a3ef  retn
```
