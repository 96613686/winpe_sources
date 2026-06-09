# FreeMemory

- ea: `0x180004b80`
- end: `0x180004c9c`
- name: `FreeMemory`
- size: `284`
- prototype: `__int64 __fastcall(LPVOID *, int, char)`
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x180001dc0`
- `0x180003520`
- `0x180003800`
- `0x180003ac0`
- `0x180003f50`
- `0x180004260`
- `0x180004a50`
- `0x180004f00`
- `0x180004fa0`
- `0x18000b894`
- `0x18000be70`
- `0x18000c6f0`
- `0x18000cb50`
- `0x18000cca0`
- `0x18000cd80`
- `0x18000ce80`
- `0x18000d2d0`
- `0x18000d360`
- `0x18000d3d0`

## callees

- `0x180004b80`
- `0x180004cb0`
- `0x18000b774`
- `0x18000b800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb7`

## pseudocode

```c
__int64 __fastcall FreeMemory(LPVOID *a1, int a2, char a3)
{
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rbx
  int v8; // r8d
  DWORD LastError; // eax
  int v11; // r8d
  DWORD v12; // eax
  int v13; // r8d

  v6 = 1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap || (v12 = GetLastError()) == 0 )
    {
      v6 = HeapFree(ProcessHeap, 0, *a1);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&WPP_GLOBAL_Control, v8, a2, a3, (char)*a1);
        *a1 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v11, a2, a3, (char)*a1, LastError);
      }
    }
    else
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v13, a2, a3, v12);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180004b80  push    rbx
0x180004b82  push    rbp
0x180004b83  push    rsi
0x180004b84  push    rdi
0x180004b85  sub     rsp, 48h
0x180004b89  cmp     qword ptr [rcx], 0
0x180004b8d  mov     esi, r8d
0x180004b90  mov     rbp, rdx
0x180004b93  mov     rdi, rcx
0x180004b96  mov     ebx, 1
0x180004b9b  jz      short loc_180004BE5
0x180004b9d  call    cs:__imp_GetProcessHeap
0x180004ba3  mov     rbx, rax
0x180004ba6  test    rax, rax
0x180004ba9  jz      loc_180004C36
0x180004baf  mov     r8, [rdi]; lpMem
0x180004bb2  xor     edx, edx; dwFlags
0x180004bb4  mov     rcx, rbx; hHeap
0x180004bb7  call    cs:__imp_HeapFree
0x180004bbd  mov     ebx, eax
0x180004bbf  test    eax, eax
0x180004bc1  jz      short loc_180004BF0
0x180004bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bca  lea     rdx, WPP_GLOBAL_Control
0x180004bd1  cmp     rcx, rdx
0x180004bd4  jz      short loc_180004BE0
0x180004bd6  test    byte ptr [rcx+1Ch], 2
0x180004bda  jnz     loc_180004C7F
0x180004be0  xor     ecx, ecx
0x180004be2  mov     [rdi], rcx
0x180004be5  mov     eax, ebx
0x180004be7  add     rsp, 48h
0x180004beb  pop     rdi
0x180004bec  pop     rsi
0x180004bed  pop     rbp
0x180004bee  pop     rbx
0x180004bef  retn
0x180004bf0  call    cs:__imp_GetLastError
0x180004bf6  test    eax, eax
0x180004bf8  jz      short loc_180004BE5
0x180004bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c01  lea     rdx, WPP_GLOBAL_Control
0x180004c08  cmp     rcx, rdx
0x180004c0b  jz      short loc_180004BE5
0x180004c0d  test    byte ptr [rcx+1Ch], 4
0x180004c11  jz      short loc_180004BE5
0x180004c13  mov     rcx, [rcx+10h]
0x180004c17  mov     edx, 0Fh
0x180004c1c  mov     [rsp+68h+var_38], eax
0x180004c20  mov     r9, rbp
0x180004c23  mov     rax, [rdi]
0x180004c26  mov     [rsp+68h+var_40], rax
0x180004c2b  mov     [rsp+68h+var_48], esi
0x180004c2f  call    WPP_SF_sdqd
0x180004c34  jmp     short loc_180004BE5
0x180004c36  call    cs:__imp_GetLastError
0x180004c3c  test    eax, eax
0x180004c3e  jz      loc_180004BAF
0x180004c44  xor     ecx, ecx
0x180004c46  mov     ebx, ecx
0x180004c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c4f  lea     rdx, WPP_GLOBAL_Control
0x180004c56  cmp     rcx, rdx
0x180004c59  jz      short loc_180004BE5
0x180004c5b  test    byte ptr [rcx+1Ch], 4
0x180004c5f  jz      short loc_180004BE5
0x180004c61  mov     rcx, [rcx+10h]
0x180004c65  mov     edx, 0Dh
0x180004c6a  mov     dword ptr [rsp+68h+var_40], eax
0x180004c6e  mov     r9, rbp
0x180004c71  mov     [rsp+68h+var_48], esi
0x180004c75  call    WPP_SF_sdd
0x180004c7a  jmp     loc_180004BE5
0x180004c7f  mov     rax, [rdi]
0x180004c82  mov     r9, rbp
0x180004c85  mov     rcx, [rcx+10h]
0x180004c89  mov     [rsp+68h+var_40], rax
0x180004c8e  mov     [rsp+68h+var_48], esi
0x180004c92  call    WPP_SF_sdq
0x180004c97  jmp     loc_180004BE0
```
