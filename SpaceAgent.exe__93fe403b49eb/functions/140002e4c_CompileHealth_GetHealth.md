# CompileHealth_GetHealth

- ea: `0x140002e4c`
- end: `0x140002f86`
- name: `CompileHealth_GetHealth`
- size: `314`
- prototype: `_BOOL8 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002db4`

## callees

- `0x140002e4c`
- `0x140007de4`
- `0x1400083dc`
- `0x140008454`
- `0x140014988`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140002eea`
- `KERNEL32!LocalFree` at `0x140002f3c`
- `KERNEL32!LocalFree` at `0x140002eea`
- `KERNEL32!LocalFree` at `0x140002f3c`
- `KERNEL32!SetLastError` at `0x140002f76`
- `KERNEL32!SetLastError` at `0x140002f76`
- `KERNEL32!GetLastError` at `0x140002e92`
- `KERNEL32!GetLastError` at `0x140002f18`
- `KERNEL32!GetLastError` at `0x140002f2a`
- `KERNEL32!GetLastError` at `0x140002f50`
- `KERNEL32!GetLastError` at `0x140002f6c`
- `KERNEL32!GetLastError` at `0x140002e92`
- `KERNEL32!GetLastError` at `0x140002f18`
- `KERNEL32!GetLastError` at `0x140002f2a`
- `KERNEL32!GetLastError` at `0x140002f50`
- `KERNEL32!GetLastError` at `0x140002f6c`

## pseudocode

```c
_BOOL8 __fastcall CompileHealth_GetHealth(_DWORD *a1)
{
  __int64 *First; // rsi
  HLOCAL v3; // rax
  BOOL v4; // ebx
  DWORD LastError; // edi
  HLOCAL v6; // rax
  int Close; // eax
  _BYTE *v9; // [rsp+20h] [rbp-38h]
  void *v10; // [rsp+28h] [rbp-30h]
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  *a1 = 0;
  hMem = 0;
  First = (__int64 *)SiFindFirst(
                       (int (*)(void *, void *, void *, void *, struct _SP_IDS **))SiGetPoolIdsCallback,
                       (int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **))SiGetPoolCallback,
                       0,
                       0,
                       v9,
                       v10,
                       (struct _SU_OBJECT **)&hMem);
  if ( First != (__int64 *)-1LL || GetLastError() == 18 )
  {
    while ( 1 )
    {
      v11 = 0;
      v12 = 0;
      if ( (int)SuCompilePoolHealthState((struct _SU_POOL_OBJECT *)hMem, &v11, &v12) >= 0 )
      {
        if ( v11 == 1 )
        {
          *a1 = 1;
        }
        else if ( v11 == 2 )
        {
          *a1 = 2;
        }
      }
      v3 = LocalFree(hMem);
      hMem = 0;
      if ( v3 )
        break;
      v4 = 1;
      if ( *a1 == 1 )
        goto LABEL_13;
      if ( !(unsigned int)SuFindNext(First, (struct _SU_OBJECT **)&hMem) )
      {
        v4 = GetLastError() == 18;
        goto LABEL_13;
      }
    }
  }
  v4 = 0;
LABEL_13:
  LastError = GetLastError();
  if ( hMem )
  {
    v6 = LocalFree(hMem);
    if ( v4 )
    {
      v4 = v6 == 0;
      LastError = GetLastError();
    }
  }
  if ( First != (__int64 *)-1LL )
  {
    Close = SuFindClose((char *)First);
    if ( v4 )
    {
      v4 = Close;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x140002e4c  push    rbx
0x140002e4e  push    rsi
0x140002e4f  push    rdi
0x140002e50  sub     rsp, 40h
0x140002e54  mov     rdi, rcx
0x140002e57  mov     dword ptr [rcx], 0
0x140002e5d  lea     rax, [rsp+58h+hMem]
0x140002e62  mov     [rsp+58h+hMem], 0
0x140002e6b  lea     rcx, ?SiGetPoolIdsCallback@@YAHPEAX000PEAPEAU_SP_IDS@@@Z; int (*)(void *, void *, void *, void *, struct _SP_IDS **)
0x140002e72  mov     [rsp+58h+var_28], rax; struct _SU_OBJECT **
0x140002e77  xor     r9d, r9d; void *
0x140002e7a  lea     rdx, ?SiGetPoolCallback@@YAHPEAX000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z; int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **)
0x140002e81  xor     r8d, r8d; void *
0x140002e84  call    ?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z; SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)
0x140002e89  mov     rsi, rax
0x140002e8c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002e90  jnz     short loc_140002EA1
0x140002e92  call    cs:__imp_GetLastError
0x140002e98  cmp     eax, 12h
0x140002e9b  jnz     loc_140002F28
0x140002ea1  mov     rcx, [rsp+58h+hMem]; struct _SU_POOL_OBJECT *
0x140002ea6  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x140002eab  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x140002eb0  mov     [rsp+58h+arg_0], 0
0x140002eb8  mov     [rsp+58h+arg_8], 0
0x140002ec0  call    ?SuCompilePoolHealthState@@YAJPEAU_SU_POOL_OBJECT@@PEAI1@Z; SuCompilePoolHealthState(_SU_POOL_OBJECT *,uint *,uint *)
0x140002ec5  test    eax, eax
0x140002ec7  js      short loc_140002EE5
0x140002ec9  cmp     [rsp+58h+arg_0], 1
0x140002ece  jnz     short loc_140002ED8
0x140002ed0  mov     dword ptr [rdi], 1
0x140002ed6  jmp     short loc_140002EE5
0x140002ed8  cmp     [rsp+58h+arg_0], 2
0x140002edd  jnz     short loc_140002EE5
0x140002edf  mov     dword ptr [rdi], 2
0x140002ee5  mov     rcx, [rsp+58h+hMem]; hMem
0x140002eea  call    cs:__imp_LocalFree
0x140002ef0  mov     [rsp+58h+hMem], 0
0x140002ef9  test    rax, rax
0x140002efc  jnz     short loc_140002F28
0x140002efe  lea     ebx, [rax+1]
0x140002f01  cmp     [rdi], ebx
0x140002f03  jz      short loc_140002F2A
0x140002f05  lea     rdx, [rsp+58h+hMem]; struct _SU_OBJECT **
0x140002f0a  mov     rcx, rsi; void *
0x140002f0d  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x140002f12  mov     ebx, eax
0x140002f14  test    eax, eax
0x140002f16  jnz     short loc_140002EA1
0x140002f18  call    cs:__imp_GetLastError
0x140002f1e  cmp     eax, 12h
0x140002f21  jnz     short loc_140002F2A
0x140002f23  lea     ebx, [rax-11h]
0x140002f26  jmp     short loc_140002F2A
0x140002f28  xor     ebx, ebx
0x140002f2a  call    cs:__imp_GetLastError
0x140002f30  mov     rcx, [rsp+58h+hMem]; hMem
0x140002f35  mov     edi, eax
0x140002f37  test    rcx, rcx
0x140002f3a  jz      short loc_140002F58
0x140002f3c  call    cs:__imp_LocalFree
0x140002f42  xor     ecx, ecx
0x140002f44  test    rax, rax
0x140002f47  setz    cl
0x140002f4a  test    ebx, ebx
0x140002f4c  jz      short loc_140002F58
0x140002f4e  mov     ebx, ecx
0x140002f50  call    cs:__imp_GetLastError
0x140002f56  mov     edi, eax
0x140002f58  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140002f5c  jz      short loc_140002F74
0x140002f5e  mov     rcx, rsi; hMem
0x140002f61  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x140002f66  test    ebx, ebx
0x140002f68  jz      short loc_140002F74
0x140002f6a  mov     ebx, eax
0x140002f6c  call    cs:__imp_GetLastError
0x140002f72  mov     edi, eax
0x140002f74  mov     ecx, edi; dwErrCode
0x140002f76  call    cs:__imp_SetLastError
0x140002f7c  mov     eax, ebx
0x140002f7e  add     rsp, 40h
0x140002f82  pop     rdi
0x140002f83  pop     rsi
0x140002f84  pop     rbx
0x140002f85  retn
```
