# CDfsShellExtProp::_UpdateTextForReplicaState(HWND__ *,int,SHL_DFS_REPLICA_STATE)

- ea: `0x180009a80`
- end: `0x180009b4b`
- name: `?_UpdateTextForReplicaState@CDfsShellExtProp@@AEAAXPEAUHWND__@@HW4SHL_DFS_REPLICA_STATE@@@Z`
- size: `203`
- prototype: `void __high(HWND, int, enum SHL_DFS_REPLICA_STATE)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008b54`
- `0x180009388`
- `0x180009700`

## callees

- `0x180009a80`
- `0x18000a9a6`

## import_xrefs

- `USER32!SendMessageW` at `0x180009ae4`
- `USER32!SendMessageW` at `0x180009b37`
- `USER32!SendMessageW` at `0x180009ae4`
- `USER32!SendMessageW` at `0x180009b37`

## pseudocode

```c
LRESULT __fastcall CDfsShellExtProp::_UpdateTextForReplicaState(_QWORD *a1, HWND a2, int a3, unsigned int a4)
{
  int *v8; // rax
  unsigned int v9; // edi
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // edi
  int *v13; // rax
  LPARAM lParam; // [rsp+20h] [rbp-60h] BYREF
  int v16; // [rsp+28h] [rbp-58h]
  int *v17; // [rsp+38h] [rbp-48h]

  memset_0(&lParam, 0, 0x58u);
  HIDWORD(lParam) = a3;
  LODWORD(lParam) = 1;
  v16 = 1;
  if ( a4 <= 2 )
    v8 = (int *)a1[30];
  else
    v8 = (int *)a1[31];
  v17 = v8;
  SendMessageW(a2, 0x104Cu, 0, (LPARAM)&lParam);
  v16 = 2;
  if ( !a4 )
    goto LABEL_12;
  v9 = a4 - 1;
  if ( !v9 )
  {
LABEL_11:
    v13 = (int *)a1[32];
    goto LABEL_13;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_10:
    v13 = (int *)a1[33];
LABEL_13:
    v17 = v13;
    return SendMessageW(a2, 0x104Cu, 0, (LPARAM)&lParam);
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
LABEL_12:
    v13 = &dword_18000F72C;
    goto LABEL_13;
  }
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_11;
  if ( v12 == 1 )
    goto LABEL_10;
  return SendMessageW(a2, 0x104Cu, 0, (LPARAM)&lParam);
}

```

## disassembly

```asm
0x180009a80  push    rbp
0x180009a82  push    rbx
0x180009a83  push    rsi
0x180009a84  push    rdi
0x180009a85  push    r14
0x180009a87  mov     rbp, rsp
0x180009a8a  sub     rsp, 80h
0x180009a91  mov     r14, rdx
0x180009a94  mov     ebx, r8d
0x180009a97  xor     edx, edx; Val
0x180009a99  mov     rsi, rcx
0x180009a9c  lea     rcx, [rbp+lParam]; void *
0x180009aa0  mov     edi, r9d
0x180009aa3  lea     r8d, [rdx+58h]; Size
0x180009aa7  call    memset_0
0x180009aac  mov     dword ptr [rbp+lParam+4], ebx
0x180009aaf  mov     eax, 1
0x180009ab4  mov     dword ptr [rbp+lParam], eax
0x180009ab7  mov     [rbp+var_58], eax
0x180009aba  cmp     edi, 2
0x180009abd  jbe     short loc_180009AC8
0x180009abf  mov     rax, [rsi+0F8h]
0x180009ac6  jmp     short loc_180009ACF
0x180009ac8  mov     rax, [rsi+0F0h]
0x180009acf  mov     ebx, 104Ch
0x180009ad4  mov     [rbp+var_48], rax
0x180009ad8  mov     edx, ebx; Msg
0x180009ada  lea     r9, [rbp+lParam]; lParam
0x180009ade  xor     r8d, r8d; wParam
0x180009ae1  mov     rcx, r14; hWnd
0x180009ae4  call    cs:__imp_SendMessageW
0x180009aea  mov     [rbp+var_58], 2
0x180009af1  test    edi, edi
0x180009af3  jz      short loc_180009B20
0x180009af5  sub     edi, 1
0x180009af8  jz      short loc_180009B17
0x180009afa  sub     edi, 1
0x180009afd  jz      short loc_180009B0E
0x180009aff  sub     edi, 1
0x180009b02  jz      short loc_180009B20
0x180009b04  sub     edi, 1
0x180009b07  jz      short loc_180009B17
0x180009b09  cmp     edi, 1
0x180009b0c  jnz     short loc_180009B2B
0x180009b0e  mov     rax, [rsi+108h]
0x180009b15  jmp     short loc_180009B27
0x180009b17  mov     rax, [rsi+100h]
0x180009b1e  jmp     short loc_180009B27
0x180009b20  lea     rax, dword_18000F72C
0x180009b27  mov     [rbp+var_48], rax
0x180009b2b  lea     r9, [rbp+lParam]; lParam
0x180009b2f  xor     r8d, r8d; wParam
0x180009b32  mov     edx, ebx; Msg
0x180009b34  mov     rcx, r14; hWnd
0x180009b37  call    cs:__imp_SendMessageW
0x180009b3d  add     rsp, 80h
0x180009b44  pop     r14
0x180009b46  pop     rdi
0x180009b47  pop     rsi
0x180009b48  pop     rbx
0x180009b49  pop     rbp
0x180009b4a  retn
```
