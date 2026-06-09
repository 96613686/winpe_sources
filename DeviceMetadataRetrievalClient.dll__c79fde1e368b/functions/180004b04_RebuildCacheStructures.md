# RebuildCacheStructures

- ea: `0x180004b04`
- end: `0x180004c3b`
- name: `RebuildCacheStructures`
- size: `311`
- prototype: `__int64 __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004320`

## callees

- `0x180003514`
- `0x1800038c8`
- `0x180003b58`
- `0x180004b04`
- `0x180004e2c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004b9d`
- `KERNEL32!GetProcessHeap` at `0x180004bb8`
- `KERNEL32!GetProcessHeap` at `0x180004bd3`
- `KERNEL32!GetProcessHeap` at `0x180004bea`
- `KERNEL32!GetProcessHeap` at `0x180004b9d`
- `KERNEL32!GetProcessHeap` at `0x180004bb8`
- `KERNEL32!GetProcessHeap` at `0x180004bd3`
- `KERNEL32!GetProcessHeap` at `0x180004bea`
- `KERNEL32!HeapFree` at `0x180004bab`
- `KERNEL32!HeapFree` at `0x180004bc6`
- `KERNEL32!HeapFree` at `0x180004be1`
- `KERNEL32!HeapFree` at `0x180004bf8`
- `KERNEL32!HeapFree` at `0x180004bab`
- `KERNEL32!HeapFree` at `0x180004bc6`
- `KERNEL32!HeapFree` at `0x180004be1`
- `KERNEL32!HeapFree` at `0x180004bf8`

## pseudocode

```c
__int64 __fastcall RebuildCacheStructures(LPCWSTR *a1)
{
  unsigned __int16 **v1; // r15
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  unsigned __int16 *v5; // r9
  __int64 v6; // rdx
  WCHAR *v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rbx
  HANDLE v10; // rax
  unsigned __int16 *v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v13; // rbx
  HANDLE v14; // rax

  v1 = (unsigned __int16 **)(a1 + 3);
  if ( (unsigned int)FSRemoveFile((unsigned __int16 *)a1[3]) )
  {
    if ( (unsigned int)FSRemoveDirPath(*a1) )
    {
      v7 = (WCHAR *)*a1;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
      v9 = (unsigned __int16 *)a1[2];
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v9);
      v11 = (unsigned __int16 *)a1[4];
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
      v13 = *v1;
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
      *a1 = 0;
      a1[2] = 0;
      a1[4] = 0;
      *v1 = 0;
      return (unsigned int)BuildCacheDirectoryStructure(a1, a1 + 2, a1 + 4, v1);
    }
    v3 = 13;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = (unsigned __int16 *)*a1;
      v6 = 33;
      goto LABEL_5;
    }
  }
  else
  {
    v3 = 13;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = *v1;
      v6 = 32;
LABEL_5:
      WPP_SF_S(v4[2], v6, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, v5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180004b04  push    rbx
0x180004b06  push    rsi
0x180004b07  push    rdi
0x180004b08  push    r14
0x180004b0a  push    r15
0x180004b0c  sub     rsp, 20h
0x180004b10  lea     r15, [rcx+18h]
0x180004b14  mov     r14, rcx
0x180004b17  mov     rcx, [r15]; unsigned __int16 *
0x180004b1a  call    FSRemoveFile
0x180004b1f  test    eax, eax
0x180004b21  jnz     short loc_180004B62
0x180004b23  lea     ebx, [rax+0Dh]
0x180004b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b2d  lea     rax, WPP_GLOBAL_Control
0x180004b34  cmp     rcx, rax
0x180004b37  jz      loc_180004C2D
0x180004b3d  test    byte ptr [rcx+1Ch], 1
0x180004b41  jz      loc_180004C2D
0x180004b47  mov     r9, [r15]
0x180004b4a  lea     edx, [rbx+13h]
0x180004b4d  mov     rcx, [rcx+10h]
0x180004b51  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180004b58  call    WPP_SF_S
0x180004b5d  jmp     loc_180004C2D
0x180004b62  mov     rcx, [r14]
0x180004b65  call    FSRemoveDirPath
0x180004b6a  test    eax, eax
0x180004b6c  jnz     short loc_180004B9A
0x180004b6e  lea     ebx, [rax+0Dh]
0x180004b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b78  lea     rax, WPP_GLOBAL_Control
0x180004b7f  cmp     rcx, rax
0x180004b82  jz      loc_180004C2D
0x180004b88  test    byte ptr [rcx+1Ch], 1
0x180004b8c  jz      loc_180004C2D
0x180004b92  mov     r9, [r14]
0x180004b95  lea     edx, [rbx+14h]
0x180004b98  jmp     short loc_180004B4D
0x180004b9a  mov     rbx, [r14]
0x180004b9d  call    cs:__imp_GetProcessHeap
0x180004ba3  mov     r8, rbx; lpMem
0x180004ba6  xor     edx, edx; dwFlags
0x180004ba8  mov     rcx, rax; hHeap
0x180004bab  call    cs:__imp_HeapFree
0x180004bb1  lea     rsi, [r14+10h]
0x180004bb5  mov     rbx, [rsi]
0x180004bb8  call    cs:__imp_GetProcessHeap
0x180004bbe  mov     r8, rbx; lpMem
0x180004bc1  xor     edx, edx; dwFlags
0x180004bc3  mov     rcx, rax; hHeap
0x180004bc6  call    cs:__imp_HeapFree
0x180004bcc  lea     rdi, [r14+20h]
0x180004bd0  mov     rbx, [rdi]
0x180004bd3  call    cs:__imp_GetProcessHeap
0x180004bd9  mov     r8, rbx; lpMem
0x180004bdc  xor     edx, edx; dwFlags
0x180004bde  mov     rcx, rax; hHeap
0x180004be1  call    cs:__imp_HeapFree
0x180004be7  mov     rbx, [r15]
0x180004bea  call    cs:__imp_GetProcessHeap
0x180004bf0  mov     r8, rbx; lpMem
0x180004bf3  xor     edx, edx; dwFlags
0x180004bf5  mov     rcx, rax; hHeap
0x180004bf8  call    cs:__imp_HeapFree
0x180004bfe  mov     r9, r15; unsigned __int16 **
0x180004c01  mov     qword ptr [r14], 0
0x180004c08  mov     r8, rdi; unsigned __int16 **
0x180004c0b  mov     qword ptr [rsi], 0
0x180004c12  mov     rdx, rsi; unsigned __int16 **
0x180004c15  mov     qword ptr [rdi], 0
0x180004c1c  mov     rcx, r14; unsigned __int16 **
0x180004c1f  mov     qword ptr [r15], 0
0x180004c26  call    ?BuildCacheDirectoryStructure@@YAKPEAPEAG000@Z; BuildCacheDirectoryStructure(ushort * *,ushort * *,ushort * *,ushort * *)
0x180004c2b  mov     ebx, eax
0x180004c2d  mov     eax, ebx
0x180004c2f  add     rsp, 20h
0x180004c33  pop     r15
0x180004c35  pop     r14
0x180004c37  pop     rdi
0x180004c38  pop     rsi
0x180004c39  pop     rbx
0x180004c3a  retn
```
