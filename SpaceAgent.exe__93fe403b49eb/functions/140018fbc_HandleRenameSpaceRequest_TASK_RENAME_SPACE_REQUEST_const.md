# HandleRenameSpaceRequest(TASK_RENAME_SPACE_REQUEST const *)

- ea: `0x140018fbc`
- end: `0x140019133`
- name: `?HandleRenameSpaceRequest@@YAHPEBUTASK_RENAME_SPACE_REQUEST@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(const struct TASK_RENAME_SPACE_REQUEST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x140017d70`

## callees

- `0x140008190`
- `0x14000a440`
- `0x140012e28`
- `0x140017044`
- `0x14001832c`
- `0x140018fbc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400190dc`
- `KERNEL32!LocalFree` at `0x140019100`
- `KERNEL32!LocalFree` at `0x1400190dc`
- `KERNEL32!LocalFree` at `0x140019100`
- `KERNEL32!SetLastError` at `0x140018ffc`
- `KERNEL32!SetLastError` at `0x14001911e`
- `KERNEL32!SetLastError` at `0x140018ffc`
- `KERNEL32!SetLastError` at `0x14001911e`
- `KERNEL32!GetLastError` at `0x1400190cc`
- `KERNEL32!GetLastError` at `0x1400190f0`
- `KERNEL32!GetLastError` at `0x140019114`
- `KERNEL32!GetLastError` at `0x1400190cc`
- `KERNEL32!GetLastError` at `0x1400190f0`
- `KERNEL32!GetLastError` at `0x140019114`

## pseudocode

```c
__int64 __fastcall HandleRenameSpaceRequest(const struct TASK_RENAME_SPACE_REQUEST *a1)
{
  unsigned int *v2; // rsi
  struct _SU_SPACE_OBJECT *v3; // rdi
  unsigned int v4; // ebx
  DWORD v5; // ecx
  unsigned int Pool; // eax
  unsigned int v7; // r8d
  int SpaceFiltered; // eax
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rax
  DWORD LastError; // ebp
  HLOCAL v12; // rax
  HLOCAL v13; // rax
  struct _SU_SPACE_OBJECT *v15; // [rsp+40h] [rbp+8h] BYREF
  struct _SU_POOL_OBJECT *v16; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  v16 = 0;
  v15 = 0;
  v4 = IssueProgressStringResult(32893);
  if ( v4 )
  {
    if ( *(_QWORD *)a1 != 576 )
    {
      v4 = 0;
      v5 = 24;
LABEL_4:
      SetLastError(v5);
      goto LABEL_14;
    }
    Pool = SiGetPool((struct _GUID *)a1 + 1, 0, &v16);
    v2 = (unsigned int *)v16;
    v4 = Pool;
    if ( Pool )
    {
      SpaceFiltered = SuGetSpaceFiltered(v16, (struct _GUID *)a1 + 2, v7, &v15);
      v3 = v15;
      v4 = SpaceFiltered;
      if ( SpaceFiltered )
      {
        v9 = (unsigned __int16 *)((char *)v15 + 112);
        *((_WORD *)a1 + 279) = 0;
        v5 = StringCchCopyW(v9, 0x100u, (const unsigned __int16 *)a1 + 24);
        if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147024774 )
        {
          v4 = 0;
          if ( (v5 & 0x1FFF0000) == 0x70000 )
            v5 = (unsigned __int16)v5;
          goto LABEL_4;
        }
        LOWORD(v15) = *((_WORD *)a1 + 280);
        v10 = *((_QWORD *)a1 + 71);
        if ( v10 > *((_QWORD *)v3 + 342) )
          *((_QWORD *)v3 + 342) = v10;
        v4 = SuSetSpaceEx(v3, (unsigned __int16 *)&v15, v2[679]);
      }
    }
  }
LABEL_14:
  LastError = GetLastError();
  if ( v3 )
  {
    v12 = LocalFree(v3);
    if ( v4 )
    {
      v4 = v12 == 0;
      LastError = GetLastError();
    }
  }
  if ( v2 )
  {
    v13 = LocalFree(v2);
    if ( v4 )
    {
      v4 = v13 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x140018fbc  mov     [rsp+arg_10], rbx
0x140018fc1  push    rbp
0x140018fc2  push    rsi
0x140018fc3  push    rdi
0x140018fc4  sub     rsp, 20h
0x140018fc8  mov     rbp, rcx
0x140018fcb  xor     esi, esi
0x140018fcd  xor     edi, edi
0x140018fcf  mov     [rsp+38h+arg_8], rsi
0x140018fd4  mov     ecx, 807Dh
0x140018fd9  mov     [rsp+38h+arg_0], rdi
0x140018fde  call    IssueProgressStringResult
0x140018fe3  mov     ebx, eax
0x140018fe5  test    eax, eax
0x140018fe7  jz      loc_1400190CC
0x140018fed  cmp     qword ptr [rbp+0], 240h
0x140018ff5  jz      short loc_140019007
0x140018ff7  xor     ebx, ebx
0x140018ff9  lea     ecx, [rsi+18h]; dwErrCode
0x140018ffc  call    cs:__imp_SetLastError
0x140019002  jmp     loc_1400190CC
0x140019007  lea     rcx, [rbp+10h]; struct _GUID *
0x14001900b  xor     edx, edx; unsigned int
0x14001900d  lea     r8, [rsp+38h+arg_8]; struct _SU_POOL_OBJECT **
0x140019012  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x140019017  mov     rsi, [rsp+38h+arg_8]
0x14001901c  mov     ebx, eax
0x14001901e  test    eax, eax
0x140019020  jz      loc_1400190CC
0x140019026  lea     rdx, [rbp+20h]; struct _GUID *
0x14001902a  mov     rcx, rsi; struct _SU_POOL_OBJECT *
0x14001902d  lea     r9, [rsp+38h+arg_0]; struct _SU_SPACE_OBJECT **
0x140019032  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140019037  mov     rdi, [rsp+38h+arg_0]
0x14001903c  mov     ebx, eax
0x14001903e  test    eax, eax
0x140019040  jz      loc_1400190CC
0x140019046  lea     r8, [rbp+30h]; unsigned __int16 *
0x14001904a  xor     eax, eax
0x14001904c  lea     rcx, [rdi+70h]; unsigned __int16 *
0x140019050  mov     [r8+1FEh], ax
0x140019058  mov     edx, 100h; unsigned __int64
0x14001905d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140019062  mov     edx, 80000000h
0x140019067  mov     ecx, eax
0x140019069  add     eax, edx
0x14001906b  test    edx, eax
0x14001906d  jnz     short loc_140019093
0x14001906f  cmp     ecx, 8007007Ah
0x140019075  jz      short loc_140019093
0x140019077  mov     eax, ecx
0x140019079  xor     ebx, ebx
0x14001907b  and     eax, 1FFF0000h
0x140019080  cmp     eax, 70000h
0x140019085  jnz     loc_140018FFC
0x14001908b  movzx   ecx, cx
0x14001908e  jmp     loc_140018FFC
0x140019093  movzx   eax, word ptr [rbp+230h]
0x14001909a  mov     word ptr [rsp+38h+arg_0], ax
0x14001909f  mov     rax, [rbp+238h]
0x1400190a6  cmp     rax, [rdi+0AB0h]
0x1400190ad  jbe     short loc_1400190B6
0x1400190af  mov     [rdi+0AB0h], rax
0x1400190b6  mov     r8d, [rsi+0A9Ch]; unsigned __int64
0x1400190bd  lea     rdx, [rsp+38h+arg_0]; unsigned __int16 *
0x1400190c2  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x1400190c5  call    ?SuSetSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@PEAG_K@Z; SuSetSpaceEx(_SU_SPACE_OBJECT *,ushort *,unsigned __int64)
0x1400190ca  mov     ebx, eax
0x1400190cc  call    cs:__imp_GetLastError
0x1400190d2  mov     ebp, eax
0x1400190d4  test    rdi, rdi
0x1400190d7  jz      short loc_1400190F8
0x1400190d9  mov     rcx, rdi; hMem
0x1400190dc  call    cs:__imp_LocalFree
0x1400190e2  xor     ecx, ecx
0x1400190e4  test    rax, rax
0x1400190e7  setz    cl
0x1400190ea  test    ebx, ebx
0x1400190ec  jz      short loc_1400190F8
0x1400190ee  mov     ebx, ecx
0x1400190f0  call    cs:__imp_GetLastError
0x1400190f6  mov     ebp, eax
0x1400190f8  test    rsi, rsi
0x1400190fb  jz      short loc_14001911C
0x1400190fd  mov     rcx, rsi; hMem
0x140019100  call    cs:__imp_LocalFree
0x140019106  xor     ecx, ecx
0x140019108  test    rax, rax
0x14001910b  setz    cl
0x14001910e  test    ebx, ebx
0x140019110  jz      short loc_14001911C
0x140019112  mov     ebx, ecx
0x140019114  call    cs:__imp_GetLastError
0x14001911a  mov     ebp, eax
0x14001911c  mov     ecx, ebp; dwErrCode
0x14001911e  call    cs:__imp_SetLastError
0x140019124  mov     eax, ebx
0x140019126  mov     rbx, [rsp+38h+arg_10]
0x14001912b  add     rsp, 20h
0x14001912f  pop     rdi
0x140019130  pop     rsi
0x140019131  pop     rbp
0x140019132  retn
```
