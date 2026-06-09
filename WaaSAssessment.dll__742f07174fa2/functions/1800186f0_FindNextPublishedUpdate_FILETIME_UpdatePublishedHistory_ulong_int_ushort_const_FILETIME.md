# FindNextPublishedUpdate(_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,_FILETIME *)

- ea: `0x1800186f0`
- end: `0x1800187ff`
- name: `?FindNextPublishedUpdate@@YAJU_FILETIME@@PEAUUpdatePublishedHistory@@KHPEBGPEAU1@@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct _FILETIME, struct UpdatePublishedHistory *, unsigned int, int, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800070d0`
- `0x180008c40`

## callees

- `0x1800186f0`
- `0x180018808`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001875b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001875b`

## pseudocode

```c
__int64 __fastcall FindNextPublishedUpdate(
        FILETIME a1,
        struct UpdatePublishedHistory *a2,
        unsigned int a3,
        int a4,
        char *a5,
        struct _FILETIME *a6)
{
  int DaysBetweenFileTimes; // esi
  unsigned int v7; // r12d
  unsigned int v8; // edi
  __int64 v12; // rbx
  char *v13; // r14
  char *v14; // rax
  char *v15; // r8
  int v16; // edx
  int v17; // ecx
  struct _FILETIME v18; // rdx
  FILETIME FileTime1; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+18h] BYREF

  FileTime1 = a1;
  DaysBetweenFileTimes = 0;
  v7 = -1;
  v8 = 0;
  for ( *a6 = a1; v8 < a3; ++v8 )
  {
    v12 = 1056LL * (int)v8;
    if ( !a4 || *(_DWORD *)((char *)a2 + v12 + 1040) )
    {
      v13 = (char *)a2 + v12;
      if ( CompareFileTime(&FileTime1, (const FILETIME *)((char *)a2 + v12 + 1048)) <= 0 )
      {
        if ( a4 )
          goto LABEL_10;
        v14 = (char *)a2 + v12 + 520;
        v15 = (char *)(a5 - v14);
        do
        {
          v16 = *(unsigned __int16 *)&v15[(_QWORD)v14];
          v17 = *(unsigned __int16 *)v14 - v16;
          if ( v17 )
            break;
          v14 += 2;
        }
        while ( v16 );
        if ( !v17 )
        {
LABEL_10:
          v18 = (struct _FILETIME)*((_QWORD *)v13 + 131);
          v21 = 0;
          DaysBetweenFileTimes = GetDaysBetweenFileTimes(FileTime1, v18, &v21);
          if ( DaysBetweenFileTimes >= 0 && v21 && v21 < v7 )
          {
            v7 = v21;
            *a6 = *(struct _FILETIME *)(v13 + 1048);
          }
        }
      }
    }
  }
  return (unsigned int)DaysBetweenFileTimes;
}

```

## disassembly

```asm
0x1800186f0  mov     [rsp+arg_8], rbx
0x1800186f5  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rcx
0x1800186fa  push    rbp
0x1800186fb  push    rsi
0x1800186fc  push    rdi
0x1800186fd  push    r12
0x1800186ff  push    r13
0x180018701  push    r14
0x180018703  push    r15
0x180018705  sub     rsp, 20h
0x180018709  mov     rax, [rsp+58h+arg_28]
0x180018711  xor     esi, esi
0x180018713  or      r12d, 0FFFFFFFFh
0x180018717  xor     edi, edi
0x180018719  mov     r15d, r9d
0x18001871c  mov     r13d, r8d
0x18001871f  mov     rbp, rdx
0x180018722  mov     [rax], rcx
0x180018725  test    r8d, r8d
0x180018728  jz      loc_1800187E8
0x18001872e  movsxd  rax, edi
0x180018731  imul    rbx, rax, 420h
0x180018738  test    r15d, r15d
0x18001873b  jz      short loc_18001874B
0x18001873d  cmp     dword ptr [rbx+rbp+410h], 0
0x180018745  jz      loc_1800187DD
0x18001874b  lea     r14, [rbx+rbp]
0x18001874f  lea     rdx, [r14+418h]; lpFileTime2
0x180018756  lea     rcx, [rsp+58h+FileTime1]; lpFileTime1
0x18001875b  call    cs:__imp_CompareFileTime
0x180018761  test    eax, eax
0x180018763  jg      short loc_1800187DD
0x180018765  test    r15d, r15d
0x180018768  jnz     short loc_180018797
0x18001876a  mov     r8, [rsp+58h+arg_20]
0x180018772  lea     rax, [rbp+208h]
0x180018779  add     rax, rbx
0x18001877c  sub     r8, rax
0x18001877f  movzx   ecx, word ptr [rax]
0x180018782  movzx   edx, word ptr [rax+r8]
0x180018787  sub     ecx, edx
0x180018789  jnz     short loc_180018793
0x18001878b  add     rax, 2
0x18001878f  test    edx, edx
0x180018791  jnz     short loc_18001877F
0x180018793  test    ecx, ecx
0x180018795  jnz     short loc_1800187DD
0x180018797  mov     rdx, [r14+418h]; struct _FILETIME
0x18001879e  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x1800187a3  mov     rcx, qword ptr [rsp+58h+FileTime1.dwLowDateTime]; struct _FILETIME
0x1800187a8  mov     [rsp+58h+arg_10], 0
0x1800187b0  call    ?GetDaysBetweenFileTimes@@YAJU_FILETIME@@0PEAK@Z; GetDaysBetweenFileTimes(_FILETIME,_FILETIME,ulong *)
0x1800187b5  mov     esi, eax
0x1800187b7  test    eax, eax
0x1800187b9  js      short loc_1800187DD
0x1800187bb  mov     ecx, [rsp+58h+arg_10]
0x1800187bf  test    ecx, ecx
0x1800187c1  jz      short loc_1800187DD
0x1800187c3  cmp     ecx, r12d
0x1800187c6  jnb     short loc_1800187DD
0x1800187c8  mov     rax, [rsp+58h+arg_28]
0x1800187d0  mov     r12d, ecx
0x1800187d3  mov     rcx, [r14+418h]
0x1800187da  mov     [rax], rcx
0x1800187dd  inc     edi
0x1800187df  cmp     edi, r13d
0x1800187e2  jb      loc_18001872E
0x1800187e8  mov     rbx, [rsp+58h+arg_8]
0x1800187ed  mov     eax, esi
0x1800187ef  add     rsp, 20h
0x1800187f3  pop     r15
0x1800187f5  pop     r14
0x1800187f7  pop     r13
0x1800187f9  pop     r12
0x1800187fb  pop     rdi
0x1800187fc  pop     rsi
0x1800187fd  pop     rbp
0x1800187fe  retn
```
