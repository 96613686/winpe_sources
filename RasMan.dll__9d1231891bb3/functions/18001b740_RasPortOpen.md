# RasPortOpen

- ea: `0x18001b740`
- end: `0x18001b851`
- name: `RasPortOpen`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x18001b740`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b788`

## pseudocode

```c
__int64 __fastcall RasPortOpen(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD CurrentProcessId; // eax
  DWORD v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  int v12; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  v7 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v12 = 1;
  v8 = SubmitLocalRequest(1u, a1, a3, v7, v12, a2);
  v9 = v8;
  if ( !v8 )
    goto LABEL_14;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_14:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 93, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001b740  push    rbx
0x18001b742  push    rbp
0x18001b743  push    rsi
0x18001b744  push    rdi
0x18001b745  push    r15
0x18001b747  sub     rsp, 30h
0x18001b74b  mov     rdi, r8
0x18001b74e  mov     rsi, rdx
0x18001b751  mov     rbp, rcx
0x18001b754  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b75b  lea     r15, WPP_GLOBAL_Control
0x18001b762  cmp     rcx, r15
0x18001b765  jz      short loc_18001B788
0x18001b767  test    byte ptr [rcx+1Ch], 40h
0x18001b76b  jz      short loc_18001B788
0x18001b76d  cmp     byte ptr [rcx+19h], 6
0x18001b771  jb      short loc_18001B788
0x18001b773  mov     rcx, [rcx+10h]
0x18001b777  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b77e  mov     edx, 5Ah ; 'Z'
0x18001b783  call    WPP_SF_
0x18001b788  call    cs:__imp_GetCurrentProcessId
0x18001b78e  mov     ebx, eax
0x18001b790  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b797  cmp     rcx, r15
0x18001b79a  jz      short loc_18001B7C0
0x18001b79c  test    byte ptr [rcx+1Ch], 40h
0x18001b7a0  jz      short loc_18001B7C0
0x18001b7a2  cmp     byte ptr [rcx+19h], 5
0x18001b7a6  jb      short loc_18001B7C0
0x18001b7a8  mov     rcx, [rcx+10h]
0x18001b7ac  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b7b3  mov     edx, 5Bh ; '['
0x18001b7b8  mov     r9d, eax
0x18001b7bb  call    WPP_SF_d
0x18001b7c0  mov     eax, 1
0x18001b7c5  mov     [rsp+58h+var_30], rsi
0x18001b7ca  mov     ecx, eax
0x18001b7cc  mov     [rsp+58h+var_38], eax
0x18001b7d0  mov     r9d, ebx
0x18001b7d3  mov     r8, rdi
0x18001b7d6  mov     rdx, rbp
0x18001b7d9  call    SubmitLocalRequest
0x18001b7de  mov     ebx, eax
0x18001b7e0  test    eax, eax
0x18001b7e2  jz      short loc_18001B814
0x18001b7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7eb  cmp     rcx, r15
0x18001b7ee  jz      short loc_18001B844
0x18001b7f0  test    byte ptr [rcx+1Ch], 40h
0x18001b7f4  jz      short loc_18001B81B
0x18001b7f6  cmp     byte ptr [rcx+19h], 2
0x18001b7fa  jb      short loc_18001B81B
0x18001b7fc  mov     rcx, [rcx+10h]
0x18001b800  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b807  mov     edx, 5Ch ; '\'
0x18001b80c  mov     r9d, eax
0x18001b80f  call    WPP_SF_d
0x18001b814  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b81b  cmp     rcx, r15
0x18001b81e  jz      short loc_18001B844
0x18001b820  test    byte ptr [rcx+1Ch], 40h
0x18001b824  jz      short loc_18001B844
0x18001b826  cmp     byte ptr [rcx+19h], 6
0x18001b82a  jb      short loc_18001B844
0x18001b82c  mov     rcx, [rcx+10h]
0x18001b830  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b837  mov     edx, 5Dh ; ']'
0x18001b83c  mov     r9d, ebx
0x18001b83f  call    WPP_SF_d
0x18001b844  mov     eax, ebx
0x18001b846  add     rsp, 30h
0x18001b84a  pop     r15
0x18001b84c  pop     rdi
0x18001b84d  pop     rsi
0x18001b84e  pop     rbp
0x18001b84f  pop     rbx
0x18001b850  retn
```
