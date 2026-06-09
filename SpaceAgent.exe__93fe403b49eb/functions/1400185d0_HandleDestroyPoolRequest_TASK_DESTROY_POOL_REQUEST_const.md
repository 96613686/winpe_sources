# HandleDestroyPoolRequest(TASK_DESTROY_POOL_REQUEST const *)

- ea: `0x1400185d0`
- end: `0x140018749`
- name: `?HandleDestroyPoolRequest@@YAHPEBUTASK_DESTROY_POOL_REQUEST@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(const struct TASK_DESTROY_POOL_REQUEST *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, service_task`

## callers

- `0x140017d70`
- `0x1400183b4`

## callees

- `0x140001caf`
- `0x1400152c8`
- `0x1400161e4`
- `0x14001832c`
- `0x1400185d0`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400186d8`
- `KERNEL32!LocalFree` at `0x1400186fc`
- `KERNEL32!LocalFree` at `0x1400186d8`
- `KERNEL32!LocalFree` at `0x1400186fc`
- `KERNEL32!SetLastError` at `0x140018649`
- `KERNEL32!SetLastError` at `0x14001871a`
- `KERNEL32!SetLastError` at `0x140018649`
- `KERNEL32!SetLastError` at `0x14001871a`
- `KERNEL32!GetLastError` at `0x1400186c8`
- `KERNEL32!GetLastError` at `0x1400186ec`
- `KERNEL32!GetLastError` at `0x140018710`
- `KERNEL32!GetLastError` at `0x1400186c8`
- `KERNEL32!GetLastError` at `0x1400186ec`
- `KERNEL32!GetLastError` at `0x140018710`

## pseudocode

```c
__int64 __fastcall HandleDestroyPoolRequest(const struct TASK_DESTROY_POOL_REQUEST *a1)
{
  struct _SP_DRIVE_INFO *v2; // rdi
  unsigned int *v3; // r14
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int i; // edx
  int v7; // eax
  int v8; // eax
  DWORD LastError; // esi
  HLOCAL v10; // rax
  HLOCAL v11; // rax
  unsigned int v13; // [rsp+20h] [rbp-E0h] BYREF
  struct _SP_DRIVE_INFO *v14; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[40]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+68h] [rbp-98h]

  memset_0(v16, 0, 0xB48u);
  v2 = 0;
  v13 = 0;
  v3 = 0;
  v14 = 0;
  v15 = 0;
  v4 = IssueProgressStringResult(32885);
  if ( v4 )
  {
    if ( *(_QWORD *)a1 == 32 )
    {
      v17 = *((_OWORD *)a1 + 1);
      v5 = SuDeletePoolEx((struct _SU_POOL_OBJECT *)v16, &v13, &v14);
      v2 = v14;
      v4 = v5;
      if ( v5 )
      {
        for ( i = 0; i < v13; ++i )
        {
          v7 = *((_DWORD *)v14 + 780 * i + 658);
          if ( v7 == 7 || v7 == 4 )
          {
            v4 = IssueProgressStringResult(32886);
            if ( !v4 )
              goto LABEL_12;
            break;
          }
        }
        v8 = SuNormalizeDriveList(v13, v2, &v15);
        v3 = v15;
        v4 = v8;
      }
    }
    else
    {
      v4 = 0;
      SetLastError(0x18u);
    }
  }
LABEL_12:
  LastError = GetLastError();
  if ( v2 )
  {
    v10 = LocalFree(v2);
    if ( v4 )
    {
      v4 = v10 == 0;
      LastError = GetLastError();
    }
  }
  if ( v3 )
  {
    v11 = LocalFree(v3);
    if ( v4 )
    {
      v4 = v11 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x1400185d0  mov     [rsp-8+arg_8], rbx
0x1400185d5  mov     [rsp-8+arg_10], rsi
0x1400185da  push    rbp
0x1400185db  push    rdi
0x1400185dc  push    r14
0x1400185de  lea     rbp, [rsp-0AA0h]
0x1400185e6  sub     rsp, 0BA0h
0x1400185ed  mov     rax, cs:__security_cookie
0x1400185f4  xor     rax, rsp
0x1400185f7  mov     [rbp+0AB0h+var_20], rax
0x1400185fe  mov     rsi, rcx
0x140018601  xor     edx, edx; Val
0x140018603  lea     rcx, [rsp+0BB0h+var_B70]; void *
0x140018608  mov     r8d, 0B48h; Size
0x14001860e  call    memset_0
0x140018613  xor     edi, edi
0x140018615  mov     [rsp+0BB0h+var_B90], 0
0x14001861d  xor     r14d, r14d
0x140018620  mov     [rsp+0BB0h+var_B88], rdi
0x140018625  mov     ecx, 8075h
0x14001862a  mov     [rsp+0BB0h+var_B80], r14
0x14001862f  call    IssueProgressStringResult
0x140018634  mov     ebx, eax
0x140018636  test    eax, eax
0x140018638  jz      loc_1400186C8
0x14001863e  cmp     qword ptr [rsi], 20h ; ' '
0x140018642  jz      short loc_140018651
0x140018644  xor     ebx, ebx
0x140018646  lea     ecx, [rdi+18h]; dwErrCode
0x140018649  call    cs:__imp_SetLastError
0x14001864f  jmp     short loc_1400186C8
0x140018651  movups  xmm0, xmmword ptr [rsi+10h]
0x140018655  lea     r8, [rsp+0BB0h+var_B88]; struct _SP_DRIVE_INFO **
0x14001865a  lea     rdx, [rsp+0BB0h+var_B90]; unsigned int *
0x14001865f  lea     rcx, [rsp+0BB0h+var_B70]; struct _SU_POOL_OBJECT *
0x140018664  movdqu  [rsp+0BB0h+var_B48], xmm0
0x14001866a  call    ?SuDeletePoolEx@@YAHPEAU_SU_POOL_OBJECT@@PEAIPEAPEAU_SP_DRIVE_INFO@@@Z; SuDeletePoolEx(_SU_POOL_OBJECT *,uint *,_SP_DRIVE_INFO * *)
0x14001866f  mov     rdi, [rsp+0BB0h+var_B88]
0x140018674  mov     ebx, eax
0x140018676  test    eax, eax
0x140018678  jz      short loc_1400186C8
0x14001867a  xor     edx, edx
0x14001867c  cmp     edx, [rsp+0BB0h+var_B90]
0x140018680  jnb     short loc_1400186B0
0x140018682  mov     eax, edx
0x140018684  imul    rcx, rax, 0C30h
0x14001868b  mov     eax, [rcx+rdi+0A48h]
0x140018692  cmp     eax, 7
0x140018695  jz      short loc_1400186A0
0x140018697  cmp     eax, 4
0x14001869a  jz      short loc_1400186A0
0x14001869c  inc     edx
0x14001869e  jmp     short loc_14001867C
0x1400186a0  mov     ecx, 8076h
0x1400186a5  call    IssueProgressStringResult
0x1400186aa  mov     ebx, eax
0x1400186ac  test    eax, eax
0x1400186ae  jz      short loc_1400186C8
0x1400186b0  mov     ecx, [rsp+0BB0h+var_B90]; unsigned int
0x1400186b4  lea     r8, [rsp+0BB0h+var_B80]; unsigned int **
0x1400186b9  mov     rdx, rdi; struct _SP_DRIVE_INFO *
0x1400186bc  call    ?SuNormalizeDriveList@@YAHIPEBU_SP_DRIVE_INFO@@PEAPEAK@Z; SuNormalizeDriveList(uint,_SP_DRIVE_INFO const *,ulong * *)
0x1400186c1  mov     r14, [rsp+0BB0h+var_B80]
0x1400186c6  mov     ebx, eax
0x1400186c8  call    cs:__imp_GetLastError
0x1400186ce  mov     esi, eax
0x1400186d0  test    rdi, rdi
0x1400186d3  jz      short loc_1400186F4
0x1400186d5  mov     rcx, rdi; hMem
0x1400186d8  call    cs:__imp_LocalFree
0x1400186de  xor     ecx, ecx
0x1400186e0  test    rax, rax
0x1400186e3  setz    cl
0x1400186e6  test    ebx, ebx
0x1400186e8  jz      short loc_1400186F4
0x1400186ea  mov     ebx, ecx
0x1400186ec  call    cs:__imp_GetLastError
0x1400186f2  mov     esi, eax
0x1400186f4  test    r14, r14
0x1400186f7  jz      short loc_140018718
0x1400186f9  mov     rcx, r14; hMem
0x1400186fc  call    cs:__imp_LocalFree
0x140018702  xor     ecx, ecx
0x140018704  test    rax, rax
0x140018707  setz    cl
0x14001870a  test    ebx, ebx
0x14001870c  jz      short loc_140018718
0x14001870e  mov     ebx, ecx
0x140018710  call    cs:__imp_GetLastError
0x140018716  mov     esi, eax
0x140018718  mov     ecx, esi; dwErrCode
0x14001871a  call    cs:__imp_SetLastError
0x140018720  mov     eax, ebx
0x140018722  mov     rcx, [rbp+0AB0h+var_20]
0x140018729  xor     rcx, rsp; StackCookie
0x14001872c  call    __security_check_cookie
0x140018731  lea     r11, [rsp+0BB0h+var_10]
0x140018739  mov     rbx, [r11+28h]
0x14001873d  mov     rsi, [r11+30h]
0x140018741  mov     rsp, r11
0x140018744  pop     r14
0x140018746  pop     rdi
0x140018747  pop     rbp
0x140018748  retn
```
