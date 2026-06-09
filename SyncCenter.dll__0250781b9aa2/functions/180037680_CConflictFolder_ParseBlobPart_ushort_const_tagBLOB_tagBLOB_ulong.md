# CConflictFolder::_ParseBlobPart(ushort const *,tagBLOB *,tagBLOB *,ulong *)

- ea: `0x180037680`
- end: `0x18003771e`
- name: `?_ParseBlobPart@CConflictFolder@@AEAAJPEBGPEAUtagBLOB@@1PEAK@Z`
- size: `158`
- prototype: `__int64 __fastcall(CConflictFolder *this, const unsigned __int16 *, struct tagBLOB *, struct tagBLOB *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037724`

## callees

- `0x180034e4c`
- `0x180037680`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18003769e`
- `SHLWAPI!StrChrW` at `0x18003769e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800376ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800376ff`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_ParseBlobPart(
        CConflictFolder *this,
        const unsigned __int16 *a2,
        struct tagBLOB *a3,
        struct tagBLOB *a4,
        unsigned int *a5)
{
  PWSTR v8; // rax
  int v9; // ebx
  PWSTR v10; // rbp
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rdx

  v8 = StrChrW(a2, 0x3Au);
  v9 = -2147024809;
  v10 = v8;
  if ( v8 )
  {
    v9 = TextToBlob2(a2, v8 - a2, a3);
    if ( v9 >= 0 )
    {
      v11 = v10 + 1;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v9 = TextToBlob2(v11, v12, a4);
      if ( v9 < 0 )
      {
        CoTaskMemFree(a3->pBlobData);
        a3->pBlobData = 0;
      }
      *a5 += lstrlenW(a2);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037680  push    rbx
0x180037682  push    rbp
0x180037683  push    rsi
0x180037684  push    rdi
0x180037685  push    r14
0x180037687  push    r15
0x180037689  sub     rsp, 28h
0x18003768d  mov     rsi, rdx
0x180037690  mov     r14, r9
0x180037693  mov     rcx, rsi; pszStart
0x180037696  mov     edx, 3Ah ; ':'; wMatch
0x18003769b  mov     rdi, r8
0x18003769e  call    cs:__imp_StrChrW
0x1800376a4  xor     r15d, r15d
0x1800376a7  mov     ebx, 80070057h
0x1800376ac  mov     rbp, rax
0x1800376af  test    rax, rax
0x1800376b2  jz      short loc_18003770F
0x1800376b4  mov     rdx, rax
0x1800376b7  mov     r8, rdi; struct tagBLOB *
0x1800376ba  sub     rdx, rsi
0x1800376bd  mov     rcx, rsi; unsigned __int16 *
0x1800376c0  sar     rdx, 1; unsigned int
0x1800376c3  call    ?TextToBlob2@@YAJPEBGIPEAUtagBLOB@@@Z; TextToBlob2(ushort const *,uint,tagBLOB *)
0x1800376c8  mov     ebx, eax
0x1800376ca  test    eax, eax
0x1800376cc  js      short loc_18003770F
0x1800376ce  lea     rcx, [rbp+2]; unsigned __int16 *
0x1800376d2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800376d6  inc     rdx; unsigned int
0x1800376d9  cmp     [rcx+rdx*2], r15w
0x1800376de  jnz     short loc_1800376D6
0x1800376e0  mov     r8, r14; struct tagBLOB *
0x1800376e3  call    ?TextToBlob2@@YAJPEBGIPEAUtagBLOB@@@Z; TextToBlob2(ushort const *,uint,tagBLOB *)
0x1800376e8  mov     ebx, eax
0x1800376ea  test    eax, eax
0x1800376ec  jns     short loc_1800376FC
0x1800376ee  mov     rcx, [rdi+8]; pv
0x1800376f2  call    cs:__imp_CoTaskMemFree
0x1800376f8  mov     [rdi+8], r15
0x1800376fc  mov     rcx, rsi; lpString
0x1800376ff  call    cs:__imp_lstrlenW
0x180037705  mov     rcx, [rsp+58h+arg_20]
0x18003770d  add     [rcx], eax
0x18003770f  mov     eax, ebx
0x180037711  add     rsp, 28h
0x180037715  pop     r15
0x180037717  pop     r14
0x180037719  pop     rdi
0x18003771a  pop     rsi
0x18003771b  pop     rbp
0x18003771c  pop     rbx
0x18003771d  retn
```
