# CountUpdatesPublishedBetweenRange(_FILETIME,_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,ulong &)

- ea: `0x1800184dc`
- end: `0x1800185ad`
- name: `?CountUpdatesPublishedBetweenRange@@YAJU_FILETIME@@0PEAUUpdatePublishedHistory@@KHPEBGAEAK@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct _FILETIME, struct _FILETIME, struct UpdatePublishedHistory *, unsigned int, int, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800070d0`
- `0x180007380`
- `0x180008c40`
- `0x180008e70`

## callees

- `0x1800184dc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001856b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018581`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001856b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018581`

## pseudocode

```c
__int64 __fastcall CountUpdatesPublishedBetweenRange(
        FILETIME a1,
        FILETIME a2,
        struct UpdatePublishedHistory *a3,
        unsigned int a4,
        int a5,
        char *a6,
        unsigned int *a7)
{
  unsigned int *v7; // rdi
  int v8; // ebx
  __int64 v11; // r9
  char *v12; // rax
  char *v13; // r8
  int v14; // edx
  int v15; // ecx
  const FILETIME *v16; // rsi
  FILETIME FileTime1; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp+10h] BYREF

  FileTime2 = a2;
  FileTime1 = a1;
  v7 = a7;
  v8 = 0;
  *a7 = 0;
  if ( a4 )
  {
    while ( 1 )
    {
      v11 = 1056LL * v8;
      if ( !a5 )
        break;
      if ( *(_DWORD *)((char *)a3 + v11 + 1040) )
        goto LABEL_9;
LABEL_12:
      if ( ++v8 >= a4 )
        return 0;
    }
    v12 = (char *)a3 + v11 + 520;
    v13 = (char *)(a6 - v12);
    do
    {
      v14 = *(unsigned __int16 *)&v13[(_QWORD)v12];
      v15 = *(unsigned __int16 *)v12 - v14;
      if ( v15 )
        break;
      v12 += 2;
    }
    while ( v14 );
    if ( v15 )
      goto LABEL_12;
LABEL_9:
    v16 = (const FILETIME *)((char *)a3 + v11);
    if ( CompareFileTime(&FileTime1, (const FILETIME *)((char *)a3 + v11 + 1048)) < 0
      && CompareFileTime(v16 + 131, &FileTime2) < 0 )
    {
      ++*v7;
    }
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x1800184dc  mov     rax, rsp
0x1800184df  mov     [rax+18h], rbx
0x1800184e3  mov     [rax+20h], rbp
0x1800184e7  mov     [rax+10h], rdx
0x1800184eb  mov     [rax+8], rcx
0x1800184ef  push    rsi
0x1800184f0  push    rdi
0x1800184f1  push    r14
0x1800184f3  sub     rsp, 20h
0x1800184f7  mov     rdi, [rsp+38h+arg_30]
0x1800184fc  xor     ebx, ebx
0x1800184fe  mov     r14d, r9d
0x180018501  mov     rbp, r8
0x180018504  mov     dword ptr [rdi], 0
0x18001850a  test    r9d, r9d
0x18001850d  jz      loc_180018598
0x180018513  movsxd  rax, ebx
0x180018516  imul    r9, rax, 420h
0x18001851d  cmp     [rsp+38h+arg_20], 0
0x180018522  jz      short loc_180018531
0x180018524  cmp     dword ptr [r9+rbp+410h], 0
0x18001852d  jz      short loc_18001858D
0x18001852f  jmp     short loc_18001855B
0x180018531  mov     r8, [rsp+38h+arg_28]
0x180018536  lea     rax, [rbp+208h]
0x18001853d  add     rax, r9
0x180018540  sub     r8, rax
0x180018543  movzx   ecx, word ptr [rax]
0x180018546  movzx   edx, word ptr [rax+r8]
0x18001854b  sub     ecx, edx
0x18001854d  jnz     short loc_180018557
0x18001854f  add     rax, 2
0x180018553  test    edx, edx
0x180018555  jnz     short loc_180018543
0x180018557  test    ecx, ecx
0x180018559  jnz     short loc_18001858D
0x18001855b  lea     rsi, [r9+rbp]
0x18001855f  lea     rdx, [rsi+418h]; lpFileTime2
0x180018566  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x18001856b  call    cs:__imp_CompareFileTime
0x180018571  test    eax, eax
0x180018573  jns     short loc_18001858D
0x180018575  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18001857a  lea     rcx, [rsi+418h]; lpFileTime1
0x180018581  call    cs:__imp_CompareFileTime
0x180018587  test    eax, eax
0x180018589  jns     short loc_18001858D
0x18001858b  inc     dword ptr [rdi]
0x18001858d  inc     ebx
0x18001858f  cmp     ebx, r14d
0x180018592  jb      loc_180018513
0x180018598  mov     rbx, [rsp+38h+arg_10]
0x18001859d  xor     eax, eax
0x18001859f  mov     rbp, [rsp+38h+arg_18]
0x1800185a4  add     rsp, 20h
0x1800185a8  pop     r14
0x1800185aa  pop     rdi
0x1800185ab  pop     rsi
0x1800185ac  retn
```
