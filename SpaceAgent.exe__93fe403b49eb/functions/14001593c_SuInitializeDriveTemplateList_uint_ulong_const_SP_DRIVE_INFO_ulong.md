# SuInitializeDriveTemplateList(uint,ulong const *,_SP_DRIVE_INFO * *,ulong * *)

- ea: `0x14001593c`
- end: `0x140015a91`
- name: `?SuInitializeDriveTemplateList@@YAHIPEBKPEAPEAU_SP_DRIVE_INFO@@PEAPEAK@Z`
- size: `341`
- prototype: `__int64 __fastcall(unsigned int, const unsigned int *, struct _SP_DRIVE_INFO **, unsigned int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400183b4`
- `0x14001913c`

## callees

- `0x14001593c`
- `0x140015a98`
- `0x140015b5c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140015a5e`
- `KERNEL32!LocalFree` at `0x140015a67`
- `KERNEL32!LocalFree` at `0x140015a5e`
- `KERNEL32!LocalFree` at `0x140015a67`
- `KERNEL32!SleepEx` at `0x140015a38`
- `KERNEL32!SleepEx` at `0x140015a38`
- `KERNEL32!SetLastError` at `0x140015a78`
- `KERNEL32!SetLastError` at `0x140015a78`
- `KERNEL32!GetLastError` at `0x140015989`
- `KERNEL32!GetLastError` at `0x140015a40`
- `KERNEL32!GetLastError` at `0x140015989`
- `KERNEL32!GetLastError` at `0x140015a40`
- `KERNEL32!LocalAlloc` at `0x140015977`
- `KERNEL32!LocalAlloc` at `0x1400159a0`
- `KERNEL32!LocalAlloc` at `0x140015977`
- `KERNEL32!LocalAlloc` at `0x1400159a0`

## pseudocode

```c
__int64 __fastcall SuInitializeDriveTemplateList(
        unsigned int a1,
        const unsigned int *a2,
        struct _SP_DRIVE_INFO **a3,
        unsigned int **a4)
{
  __int64 v4; // r14
  int v5; // r13d
  struct _SP_DRIVE_INFO *v8; // rbp
  unsigned int *v9; // rdi
  unsigned int Primordials; // ebx
  DWORD LastError; // esi
  int v12; // esi
  _DWORD v14[22]; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+90h] [rbp+8h] BYREF

  v4 = a1;
  v5 = (int)a2;
  v14[0] = 0;
  v15 = 0;
  v8 = (struct _SP_DRIVE_INFO *)LocalAlloc(0x40u, 3120LL * a1);
  if ( !v8 )
  {
    v9 = 0;
LABEL_3:
    Primordials = 0;
    LastError = GetLastError();
    goto LABEL_13;
  }
  v9 = (unsigned int *)LocalAlloc(0x40u, 4 * v4);
  if ( !v9 )
    goto LABEL_3;
  v12 = 30;
  Primordials = SuInitializeDriveTemplateList_VerifyDisks(1, v4, v5, (_DWORD)v9, (__int64)&v15);
  if ( Primordials )
  {
    while ( 1 )
    {
      Primordials = SuInitializeDriveTemplateList_FindPrimordials(v4, v5, (_DWORD)v8, (_DWORD)v9, (__int64)v14);
      if ( Primordials )
      {
        if ( !v14[0] )
          break;
      }
      if ( !v12 )
        break;
      Primordials = SuInitializeDriveTemplateList_VerifyDisks(0, v4, v5, (_DWORD)v9, (__int64)&v15);
      if ( !Primordials && !v15 )
        break;
      --v12;
      SleepEx(0x3E8u, 0);
    }
  }
  LastError = GetLastError();
  if ( Primordials )
  {
    *a3 = v8;
    *a4 = v9;
    goto LABEL_15;
  }
LABEL_13:
  *a3 = 0;
  *a4 = 0;
  LocalFree(v9);
  LocalFree(v8);
LABEL_15:
  SetLastError(LastError);
  return Primordials;
}

```

## disassembly

```asm
0x14001593c  mov     rax, rsp
0x14001593f  push    rbx
0x140015940  push    rbp
0x140015941  push    rsi
0x140015942  push    rdi
0x140015943  push    r12
0x140015945  push    r13
0x140015947  push    r14
0x140015949  push    r15
0x14001594b  sub     rsp, 48h
0x14001594f  mov     r14d, ecx
0x140015952  mov     r13, rdx
0x140015955  imul    rdx, r14, 0C30h; uBytes
0x14001595c  mov     edi, 40h ; '@'
0x140015961  mov     dword ptr [rax-58h], 0
0x140015968  mov     ecx, edi; uFlags
0x14001596a  mov     dword ptr [rax+8], 0
0x140015971  mov     r15, r9
0x140015974  mov     r12, r8
0x140015977  call    cs:__imp_LocalAlloc
0x14001597d  mov     rbp, rax
0x140015980  test    rax, rax
0x140015983  jnz     short loc_140015996
0x140015985  xor     edi, edi
0x140015987  xor     ebx, ebx
0x140015989  call    cs:__imp_GetLastError
0x14001598f  mov     esi, eax
0x140015991  jmp     loc_140015A4C
0x140015996  lea     rdx, ds:0[r14*4]; uBytes
0x14001599e  mov     ecx, edi; uFlags
0x1400159a0  call    cs:__imp_LocalAlloc
0x1400159a6  mov     rdi, rax
0x1400159a9  test    rax, rax
0x1400159ac  jz      short loc_140015987
0x1400159ae  lea     rax, [rsp+88h+arg_0]
0x1400159b6  mov     esi, 1Eh
0x1400159bb  mov     r9, rdi
0x1400159be  mov     [rsp+88h+var_68], rax
0x1400159c3  mov     r8, r13
0x1400159c6  mov     edx, r14d
0x1400159c9  lea     ecx, [rsi-1Dh]
0x1400159cc  call    SuInitializeDriveTemplateList_VerifyDisks
0x1400159d1  mov     ebx, eax
0x1400159d3  test    eax, eax
0x1400159d5  jz      short loc_140015A40
0x1400159d7  lea     rax, [rsp+88h+var_58]
0x1400159dc  mov     r9, rdi
0x1400159df  mov     r8, rbp
0x1400159e2  mov     [rsp+88h+var_68], rax
0x1400159e7  mov     rdx, r13
0x1400159ea  mov     ecx, r14d
0x1400159ed  call    SuInitializeDriveTemplateList_FindPrimordials
0x1400159f2  mov     ebx, eax
0x1400159f4  test    eax, eax
0x1400159f6  jz      short loc_1400159FF
0x1400159f8  cmp     [rsp+88h+var_58], 0
0x1400159fd  jz      short loc_140015A40
0x1400159ff  test    esi, esi
0x140015a01  jz      short loc_140015A40
0x140015a03  lea     rax, [rsp+88h+arg_0]
0x140015a0b  mov     r9, rdi
0x140015a0e  mov     r8, r13
0x140015a11  mov     [rsp+88h+var_68], rax
0x140015a16  mov     edx, r14d
0x140015a19  xor     ecx, ecx
0x140015a1b  call    SuInitializeDriveTemplateList_VerifyDisks
0x140015a20  mov     ebx, eax
0x140015a22  test    eax, eax
0x140015a24  jnz     short loc_140015A2F
0x140015a26  cmp     [rsp+88h+arg_0], eax
0x140015a2d  jz      short loc_140015A40
0x140015a2f  dec     esi
0x140015a31  xor     edx, edx; bAlertable
0x140015a33  mov     ecx, 3E8h; dwMilliseconds
0x140015a38  call    cs:__imp_SleepEx
0x140015a3e  jmp     short loc_1400159D7
0x140015a40  call    cs:__imp_GetLastError
0x140015a46  mov     esi, eax
0x140015a48  test    ebx, ebx
0x140015a4a  jnz     short loc_140015A6F
0x140015a4c  mov     rcx, rdi; hMem
0x140015a4f  mov     qword ptr [r12], 0
0x140015a57  mov     qword ptr [r15], 0
0x140015a5e  call    cs:__imp_LocalFree
0x140015a64  mov     rcx, rbp; hMem
0x140015a67  call    cs:__imp_LocalFree
0x140015a6d  jmp     short loc_140015A76
0x140015a6f  mov     [r12], rbp
0x140015a73  mov     [r15], rdi
0x140015a76  mov     ecx, esi; dwErrCode
0x140015a78  call    cs:__imp_SetLastError
0x140015a7e  mov     eax, ebx
0x140015a80  add     rsp, 48h
0x140015a84  pop     r15
0x140015a86  pop     r14
0x140015a88  pop     r13
0x140015a8a  pop     r12
0x140015a8c  pop     rdi
0x140015a8d  pop     rsi
0x140015a8e  pop     rbp
0x140015a8f  pop     rbx
0x140015a90  retn
```
