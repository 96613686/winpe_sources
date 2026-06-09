# ept_delete_ex_helper

- ea: `0x180005b24`
- end: `0x180005c93`
- name: `ept_delete_ex_helper`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800014b0`

## callees

- `0x1800028f8`
- `0x1800033f0`
- `0x180003660`
- `0x180003718`
- `0x180005b24`
- `0x180007fb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c6f`

## pseudocode

```c
__int64 __fastcall ept_delete_ex_helper(
        __int64 a1,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned int a4,
        char *a5,
        char *a6,
        int a7,
        __int64 a8,
        __int64 **a9)
{
  unsigned int v9; // ebx
  __int64 *v12; // rcx
  __int64 *IFOBJNode; // rax
  __int64 *v14; // rdi
  _QWORD *v15; // r14
  __int64 PSEP; // rax
  _DWORD *v18; // rsi
  HANDLE v19; // rcx

  v9 = 0;
  *a9 = 0;
  if ( !a5 )
    return 1753;
  if ( !a6 )
    return 1753;
  v12 = *(__int64 **)(a1 + 8);
  if ( !v12 )
    return 1753;
  IFOBJNode = FindIFOBJNode(
                v12,
                (__int64)a2,
                (__int64)a3,
                a4,
                0,
                0,
                0,
                (unsigned int (__fastcall *)(__int64 *, __int64, __int64, _QWORD, int, int))ExactMatch,
                a1,
                0);
  v14 = IFOBJNode;
  if ( !IFOBJNode )
    return 1753;
  v15 = IFOBJNode + 4;
  if ( !IFOBJNode[4] )
    return 1753;
  if ( !a7 && IFOBJNode[19] && a8 - IFOBJNode[19] < (unsigned __int64)*((unsigned int *)IFOBJNode + 37) )
    return 1723;
  PSEP = FindPSEP(*v15, a5, a6);
  v18 = (_DWORD *)PSEP;
  if ( PSEP )
  {
    UnLink(v15, PSEP);
    if ( (unsigned int)IsEpmapEventEnabled((struct _EVENT_DESCRIPTOR *)&EpmapInterfaceUnregisterEvent) )
      LogpInterfaceEvent(a3, a2, a5, a6, (struct _EVENT_DESCRIPTOR *)&EpmapInterfaceUnregisterEvent);
    if ( !*v15 )
      *a9 = v14;
    v19 = hEpMapperHeap;
    v18[2] = -1159872290;
    HeapFree(v19, 0, v18);
  }
  else
  {
    return 1753;
  }
  return v9;
}

```

## disassembly

```asm
0x180005b24  mov     r11, rsp
0x180005b27  mov     [r11+10h], rdx
0x180005b2b  push    rbx
0x180005b2c  push    rsi
0x180005b2d  push    rdi
0x180005b2e  push    r13
0x180005b30  push    r14
0x180005b32  push    r15
0x180005b34  sub     rsp, 58h
0x180005b38  mov     r15, [rsp+88h+arg_40]
0x180005b40  xor     ebx, ebx
0x180005b42  mov     r13, r8
0x180005b45  mov     rax, rcx
0x180005b48  mov     [r15], rbx
0x180005b4b  cmp     [rsp+88h+arg_20], rbx
0x180005b53  jz      loc_180005C80
0x180005b59  cmp     [rsp+88h+arg_28], rbx
0x180005b61  jz      loc_180005C80
0x180005b67  mov     rcx, [rcx+8]
0x180005b6b  test    rcx, rcx
0x180005b6e  jz      loc_180005C80
0x180005b74  mov     [r11-40h], rbx
0x180005b78  mov     [r11-48h], rax
0x180005b7c  lea     rax, ExactMatch
0x180005b83  mov     [r11-50h], rax
0x180005b87  mov     [rsp+88h+var_58], ebx
0x180005b8b  mov     [rsp+88h+var_60], ebx
0x180005b8f  mov     [r11-68h], rbx
0x180005b93  call    FindIFOBJNode
0x180005b98  mov     rdi, rax
0x180005b9b  test    rax, rax
0x180005b9e  jz      loc_180005C77
0x180005ba4  lea     r14, [rax+20h]
0x180005ba8  cmp     [r14], rbx
0x180005bab  jz      loc_180005C77
0x180005bb1  cmp     [rsp+88h+arg_30], ebx
0x180005bb8  jnz     short loc_180005BED
0x180005bba  mov     rcx, [rax+98h]
0x180005bc1  test    rcx, rcx
0x180005bc4  jz      short loc_180005BED
0x180005bc6  mov     rax, [rax+98h]
0x180005bcd  mov     rcx, [rsp+88h+arg_38]
0x180005bd5  sub     rcx, rax
0x180005bd8  mov     eax, [rdi+94h]
0x180005bde  cmp     rcx, rax
0x180005be1  jnb     short loc_180005BED
0x180005be3  mov     eax, 6BBh
0x180005be8  jmp     loc_180005C85
0x180005bed  mov     r8, [rsp+88h+arg_28]
0x180005bf5  mov     rdx, [rsp+88h+arg_20]
0x180005bfd  mov     rcx, [r14]
0x180005c00  call    FindPSEP
0x180005c05  mov     rsi, rax
0x180005c08  test    rax, rax
0x180005c0b  jz      short loc_180005C77
0x180005c0d  mov     rdx, rax
0x180005c10  mov     rcx, r14
0x180005c13  call    UnLink
0x180005c18  lea     rcx, EpmapInterfaceUnregisterEvent; struct _EVENT_DESCRIPTOR *
0x180005c1f  call    ?IsEpmapEventEnabled@@YAHPEAU_EVENT_DESCRIPTOR@@@Z; IsEpmapEventEnabled(_EVENT_DESCRIPTOR *)
0x180005c24  test    eax, eax
0x180005c26  jz      short loc_180005C54
0x180005c28  mov     r9, [rsp+88h+arg_28]; char *
0x180005c30  lea     rax, EpmapInterfaceUnregisterEvent
0x180005c37  mov     r8, [rsp+88h+arg_20]; char *
0x180005c3f  mov     rcx, r13; struct _GUID *
0x180005c42  mov     rdx, [rsp+88h+arg_8]; struct _GUID *
0x180005c4a  mov     [rsp+88h+var_68], rax; struct _EVENT_DESCRIPTOR *
0x180005c4f  call    ?LogpInterfaceEvent@@YAXPEAU_GUID@@0PEAD1PEAU_EVENT_DESCRIPTOR@@@Z; LogpInterfaceEvent(_GUID *,_GUID *,char *,char *,_EVENT_DESCRIPTOR *)
0x180005c54  cmp     [r14], rbx
0x180005c57  jnz     short loc_180005C5C
0x180005c59  mov     [r15], rdi
0x180005c5c  mov     rcx, cs:hEpMapperHeap; hHeap
0x180005c63  mov     r8, rsi; lpMem
0x180005c66  xor     edx, edx; dwFlags
0x180005c68  mov     dword ptr [rsi+8], 0BADDC0DEh
0x180005c6f  call    cs:__imp_HeapFree
0x180005c75  jmp     short loc_180005C7C
0x180005c77  mov     ebx, 6D9h
0x180005c7c  mov     eax, ebx
0x180005c7e  jmp     short loc_180005C85
0x180005c80  mov     eax, 6D9h
0x180005c85  add     rsp, 58h
0x180005c89  pop     r15
0x180005c8b  pop     r14
0x180005c8d  pop     r13
0x180005c8f  pop     rdi
0x180005c90  pop     rsi
0x180005c91  pop     rbx
0x180005c92  retn
```
