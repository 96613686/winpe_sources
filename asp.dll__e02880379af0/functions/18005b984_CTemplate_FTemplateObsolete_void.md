# CTemplate::FTemplateObsolete(void)

- ea: `0x18005b984`
- end: `0x18005bacc`
- name: `?FTemplateObsolete@CTemplate@@QEAAHXZ`
- size: `328`
- prototype: `__int64 __fastcall(CTemplate *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032694`

## callees

- `0x180016b50`
- `0x180023d62`
- `0x18005b984`
- `0x180061284`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005ba57`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005ba57`
- `KERNEL32!HeapFree` at `0x18005ba9a`
- `KERNEL32!HeapFree` at `0x18005ba9a`
- `KERNEL32!CompareFileTime` at `0x18005b9e5`
- `KERNEL32!CompareFileTime` at `0x18005b9e5`

## pseudocode

```c
_BOOL8 __fastcall CTemplate::FTemplateObsolete(CTemplate *this)
{
  BOOL v1; // edi
  __int64 v2; // rbp
  __int64 v4; // rax
  __int64 v5; // rbx
  int FileAttributes; // r15d
  __int64 v7; // rcx
  int v8; // eax
  const WCHAR *v9; // rcx
  void *v10; // rbx
  DWORD SecurityDescriptorLength; // eax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp+10h] BYREF
  void *Buf2; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  if ( *((_DWORD *)this + 74) )
  {
    while ( 1 )
    {
      v4 = *((_QWORD *)this + 34);
      FileTime2 = 0;
      v5 = *(_QWORD *)(v4 + 8 * v2);
      FileAttributes = AspGetFileAttributes(*(const unsigned __int16 **)(v5 + 8), *(void **)(v5 + 32), &FileTime2, 0, 0);
      if ( CompareFileTime((const FILETIME *)(v5 + 80), &FileTime2) || FileAttributes < 0 )
        break;
      v7 = *(_QWORD *)(*((_QWORD *)this + 34) + 8 * v2);
      if ( *(_QWORD *)(v7 + 64) )
      {
        v8 = *(_DWORD *)(v7 + 72);
        v9 = *(const WCHAR **)(v7 + 8);
        Buf2 = 0;
        LODWORD(Size) = v8 & 0x3FFFFFFF;
        if ( !GetSecDescriptor(v9, &Buf2, (unsigned int *)&Size) )
        {
          v10 = Buf2;
          if ( !Buf2 )
            break;
          SecurityDescriptorLength = GetSecurityDescriptorLength(*(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(*((_QWORD *)this + 34) + 8 * v2)
                                                                                         + 64LL));
          v1 = (_DWORD)Size != SecurityDescriptorLength
            || memcmp_0(*(const void **)(*(_QWORD *)(*((_QWORD *)this + 34) + 8 * v2) + 64LL), v10, (unsigned int)Size) != 0;
          HeapFree(g_hDenaliHeap, 0, v10);
          if ( v1 )
            return v1;
        }
      }
      v2 = (unsigned int)(v2 + 1);
      if ( (unsigned int)v2 >= *((_DWORD *)this + 74) )
        return v1;
    }
    return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x18005b984  mov     [rsp+arg_18], rbx
0x18005b989  push    rbp
0x18005b98a  push    rsi
0x18005b98b  push    rdi
0x18005b98c  push    r14
0x18005b98e  push    r15
0x18005b990  sub     rsp, 30h
0x18005b994  xor     edi, edi
0x18005b996  xor     ebp, ebp
0x18005b998  mov     rsi, rcx
0x18005b99b  cmp     [rcx+128h], edi
0x18005b9a1  jbe     loc_18005BAB9
0x18005b9a7  mov     rax, [rsi+110h]
0x18005b9ae  lea     r8, [rsp+58h+FileTime2]; struct _FILETIME *
0x18005b9b3  xor     r9d, r9d; unsigned int *
0x18005b9b6  mov     qword ptr [rsp+58h+FileTime2.dwLowDateTime], 0
0x18005b9bf  mov     [rsp+58h+var_38], 0; unsigned int *
0x18005b9c8  mov     rbx, [rax+rbp*8]
0x18005b9cc  mov     rdx, [rbx+20h]; void *
0x18005b9d0  mov     rcx, [rbx+8]; unsigned __int16 *
0x18005b9d4  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x18005b9d9  lea     rcx, [rbx+50h]; lpFileTime1
0x18005b9dd  mov     r15d, eax
0x18005b9e0  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x18005b9e5  call    cs:__imp_CompareFileTime
0x18005b9eb  test    eax, eax
0x18005b9ed  jnz     loc_18005BAB4
0x18005b9f3  test    r15d, r15d
0x18005b9f6  js      loc_18005BAB4
0x18005b9fc  mov     rax, [rsi+110h]
0x18005ba03  mov     rcx, [rax+rbp*8]
0x18005ba07  cmp     qword ptr [rcx+40h], 0
0x18005ba0c  jz      loc_18005BAA4
0x18005ba12  mov     eax, [rcx+48h]
0x18005ba15  lea     r8, [rsp+58h+Size]; unsigned int *
0x18005ba1a  mov     rcx, [rcx+8]; lpFileName
0x18005ba1e  lea     rdx, [rsp+58h+Buf2]; void **
0x18005ba23  and     eax, 3FFFFFFFh
0x18005ba28  mov     [rsp+58h+Buf2], 0
0x18005ba31  mov     dword ptr [rsp+58h+Size], eax
0x18005ba35  call    ?GetSecDescriptor@@YAKPEBGPEAPEAXPEAK@Z; GetSecDescriptor(ushort const *,void * *,ulong *)
0x18005ba3a  test    eax, eax
0x18005ba3c  jnz     short loc_18005BAA4
0x18005ba3e  mov     rbx, [rsp+58h+Buf2]
0x18005ba43  test    rbx, rbx
0x18005ba46  jz      short loc_18005BAB4
0x18005ba48  mov     rax, [rsi+110h]
0x18005ba4f  mov     rcx, [rax+rbp*8]
0x18005ba53  mov     rcx, [rcx+40h]; pSecurityDescriptor
0x18005ba57  call    cs:__imp_GetSecurityDescriptorLength
0x18005ba5d  cmp     dword ptr [rsp+58h+Size], eax
0x18005ba61  jz      short loc_18005BA6A
0x18005ba63  mov     edi, 1
0x18005ba68  jmp     short loc_18005BA8E
0x18005ba6a  mov     rax, [rsi+110h]
0x18005ba71  mov     rdx, rbx; Buf2
0x18005ba74  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x18005ba79  mov     rcx, [rax+rbp*8]
0x18005ba7d  mov     rcx, [rcx+40h]; Buf1
0x18005ba81  call    memcmp_0
0x18005ba86  xor     edi, edi
0x18005ba88  test    eax, eax
0x18005ba8a  setnz   dil
0x18005ba8e  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005ba95  mov     r8, rbx; lpMem
0x18005ba98  xor     edx, edx; dwFlags
0x18005ba9a  call    cs:__imp_HeapFree
0x18005baa0  test    edi, edi
0x18005baa2  jnz     short loc_18005BAB9
0x18005baa4  inc     ebp
0x18005baa6  cmp     ebp, [rsi+128h]
0x18005baac  jb      loc_18005B9A7
0x18005bab2  jmp     short loc_18005BAB9
0x18005bab4  mov     edi, 1
0x18005bab9  mov     rbx, [rsp+58h+arg_18]
0x18005babe  mov     eax, edi
0x18005bac0  add     rsp, 30h
0x18005bac4  pop     r15
0x18005bac6  pop     r14
0x18005bac8  pop     rdi
0x18005bac9  pop     rsi
0x18005baca  pop     rbp
0x18005bacb  retn
```
