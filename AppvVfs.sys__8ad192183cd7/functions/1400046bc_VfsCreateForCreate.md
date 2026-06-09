# VfsCreateForCreate

- ea: `0x1400046bc`
- end: `0x1400049ae`
- name: `VfsCreateForCreate`
- size: `754`
- prototype: `NTSTATUS __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140003c00`

## callees

- `0x1400046bc`
- `0x14000e438`
- `0x14000eb14`
- `0x14000fd38`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!IoReplaceFileObjectName` at `0x1400048a6`
- `ntoskrnl!IoReplaceFileObjectName` at `0x1400048a6`
- `FLTMGR!FltGetInstanceContext` at `0x14000480c`
- `FLTMGR!FltGetInstanceContext` at `0x14000480c`
- `FLTMGR!FltReleaseContext` at `0x140004871`
- `FLTMGR!FltReleaseContext` at `0x140004871`

## string_xrefs

- `0x140004822`: `VfsCreateForCreate() - Failed to get instance context for instance: %p\n Status: 0x%08X`
- `0x140004884`: `VfsCreateForCreate() - Failed to create parent directories for %wZ\n Status: 0x%08X`

## pseudocode

```c
NTSTATUS __fastcall VfsCreateForCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _DWORD *a3)
{
  int v4; // eax
  NTSTATUS result; // eax
  char v8; // r12
  int v9; // r9d
  __int64 v10; // r10
  _DWORD *v11; // rdx
  int v12; // r11d
  void *v13; // rcx
  struct _FLT_INSTANCE *v14; // rcx
  NTSTATUS InstanceContext; // ebp
  __int64 v16; // r9
  const wchar_t *v17; // r8
  __int64 v18; // r14
  __int64 v19; // rdx
  int v20; // eax
  PFLT_INSTANCE v21; // [rsp+20h] [rbp-88h]
  __int64 v22; // [rsp+B8h] [rbp+10h] BYREF
  PFLT_CONTEXT Context; // [rsp+C0h] [rbp+18h] BYREF

  *a3 = 0;
  v4 = *(_DWORD *)(a2 + 76);
  LOBYTE(v22) = 0;
  LOWORD(Context) = 0;
  BYTE2(Context) = 0;
  if ( (v4 & 0xC0) != 0 && (v4 & 0x200) == 0 )
    return -1073741771;
  if ( (v4 & 4) != 0 )
    return -1073741790;
  if ( (v4 & 0x2000) != 0 || (v4 & 0x200) != 0 )
    v8 = BYTE1(Context);
  else
    v8 = (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x10000) == 0
      && *(_QWORD *)(a2 + 24) == *(_QWORD *)(a2 + 48);
  if ( (_BYTE)Context )
  {
    *a3 = 1;
    return 0;
  }
  v9 = *(_DWORD *)(a2 + 72);
  v10 = *(_QWORD *)(a2 + 16);
  v11 = *(_DWORD **)(CallbackData->Iopb->Parameters.WMI.ProviderId + 8);
  v12 = v11[4];
  if ( (v11[3] & 4) != 0 )
  {
    v11[5] |= v12 & 0xFEFFFFFF;
    v11[4] = v12 & ~v11[5];
  }
  if ( !v9 )
    return -1073741790;
  if ( v9 == 1 )
    v13 = *(void **)(v10 + 72);
  else
    v13 = *(void **)(v10 + 88);
  result = VfsAccessCheck(v13);
  if ( result >= 0 )
  {
    if ( (*(_DWORD *)(a2 + 76) & 0x10) != 0 )
    {
      v18 = a2 + 56;
    }
    else
    {
      v14 = *(struct _FLT_INSTANCE **)(a2 + 48);
      Context = 0;
      InstanceContext = FltGetInstanceContext(v14, &Context);
      if ( InstanceContext < 0 )
      {
        v16 = *(_QWORD *)(a2 + 48);
        v17 = L"VfsCreateForCreate() - Failed to get instance context for instance: %p\n Status: 0x%08X";
LABEL_24:
        LODWORD(v21) = InstanceContext;
        LogWrite(1, 0, v17, v16, v21);
        return InstanceContext;
      }
      v18 = a2 + 56;
      InstanceContext = VfsCreateParentDirectories(
                          *(_QWORD *)(a2 + 24),
                          *(_QWORD *)(a2 + 48),
                          *(_QWORD *)(a2 + 16),
                          (int)a2 + 56,
                          *((_WORD *)Context + 4));
      FltReleaseContext(Context);
      if ( InstanceContext < 0 )
      {
        v16 = a2 + 56;
        v17 = L"VfsCreateForCreate() - Failed to create parent directories for %wZ\n Status: 0x%08X";
        goto LABEL_24;
      }
    }
    if ( v8 )
    {
      result = IoReplaceFileObjectName(CallbackData->Iopb->TargetFileObject, *(PWSTR *)(v18 + 8), *(_WORD *)v18);
      if ( result < 0 )
        return result;
      *a3 = 2;
    }
    else
    {
      result = VfsCreateShadow(
                 CallbackData,
                 0,
                 *(PFLT_INSTANCE *)(a2 + 48),
                 v18,
                 0,
                 (*(_DWORD *)(a2 + 76) & 0x40) != 0,
                 (*(_DWORD *)(a2 + 76) & 0x200) != 0,
                 (*(_DWORD *)(a2 + 76) & 0x2000) != 0,
                 0,
                 *(_QWORD *)a2,
                 *(_QWORD *)(a2 + 8),
                 *(_QWORD *)(a2 + 16),
                 (__int64)&v22);
      if ( result < 0 )
        return result;
      v19 = *(_QWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 8);
      *(_DWORD *)(v19 + 20) |= *(_DWORD *)(v19 + 16);
      v20 = *(_DWORD *)(v19 + 20);
      if ( (v20 & 0x2000000) != 0 )
        *(_DWORD *)(v19 + 20) = v20 & 0xFDE0FE00 | 0x1F01FF;
      *(_DWORD *)(v19 + 16) = 0;
      CallbackData->IoStatus.Information = 2;
      CallbackData->IoStatus.Status = 0;
      *a3 = 3;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400046bc  mov     r11, rsp
0x1400046bf  mov     [r11+8], rbx
0x1400046c3  push    rbp
0x1400046c4  push    rdi
0x1400046c5  push    r12
0x1400046c7  push    r14
0x1400046c9  push    r15
0x1400046cb  sub     rsp, 80h
0x1400046d2  mov     rdi, rcx
0x1400046d5  mov     dword ptr [r8], 0
0x1400046dc  mov     eax, [rdx+4Ch]
0x1400046df  xor     ecx, ecx
0x1400046e1  mov     byte ptr [r11+10h], 0
0x1400046e6  mov     r15, r8
0x1400046e9  mov     [r11+18h], cx
0x1400046ee  mov     rbx, rdx
0x1400046f1  mov     [r11+1Ah], cl
0x1400046f5  test    al, 0C0h
0x1400046f7  jz      short loc_140004709
0x1400046f9  bt      eax, 9
0x1400046fd  jb      short loc_140004709
0x1400046ff  mov     eax, 0C0000035h
0x140004704  jmp     loc_140004995
0x140004709  test    al, 4
0x14000470b  jz      short loc_140004717
0x14000470d  mov     eax, 0C0000022h
0x140004712  jmp     loc_140004995
0x140004717  bt      eax, 0Dh
0x14000471b  jb      short loc_140004747
0x14000471d  bt      eax, 9
0x140004721  jb      short loc_140004747
0x140004723  mov     rax, [rdi+10h]
0x140004727  mov     rcx, [rax+18h]
0x14000472b  test    dword ptr [rcx+10h], 10000h
0x140004732  jz      short loc_140004739
0x140004734  xor     r12b, r12b
0x140004737  jmp     short loc_14000474F
0x140004739  mov     rax, [rdx+30h]
0x14000473d  cmp     [rdx+18h], rax
0x140004741  setz    r12b
0x140004745  jmp     short loc_14000474F
0x140004747  mov     r12b, byte ptr [rsp+0A8h+Context+1]
0x14000474f  cmp     byte ptr [rsp+0A8h+Context], 0
0x140004757  jz      short loc_140004765
0x140004759  mov     dword ptr [r8], 1
0x140004760  jmp     loc_140004993
0x140004765  mov     rcx, [rdi+10h]
0x140004769  mov     ebp, 1000000h
0x14000476e  mov     r9d, [rdx+48h]
0x140004772  mov     r10, [rdx+10h]
0x140004776  mov     rax, [rcx+18h]
0x14000477a  mov     rdx, [rax+8]
0x14000477e  mov     eax, [rcx+20h]
0x140004781  and     eax, 1
0x140004784  mov     r11d, [rdx+10h]
0x140004788  lea     ecx, ds:2[rax*2]
0x14000478f  mov     eax, [rdx+0Ch]
0x140004792  mov     r8d, ecx
0x140004795  or      r8d, ebp
0x140004798  test    ebp, r11d
0x14000479b  cmovz   r8d, ecx
0x14000479f  test    al, 4
0x1400047a1  jz      short loc_1400047BB
0x1400047a3  mov     eax, r11d
0x1400047a6  btr     eax, 18h
0x1400047aa  or      [rdx+14h], eax
0x1400047ad  mov     eax, [rdx+14h]
0x1400047b0  not     eax
0x1400047b2  and     eax, r11d
0x1400047b5  mov     [rdx+10h], eax
0x1400047b8  xor     r8d, r8d
0x1400047bb  test    r9d, r9d
0x1400047be  jz      loc_14000470D
0x1400047c4  lea     eax, [r9-1]
0x1400047c8  test    eax, eax
0x1400047ca  jnz     short loc_1400047D2
0x1400047cc  mov     rcx, [r10+48h]
0x1400047d0  jmp     short loc_1400047D6
0x1400047d2  mov     rcx, [r10+58h]; SecurityDescriptor
0x1400047d6  mov     r9b, 1
0x1400047d9  mov     rdx, rdi
0x1400047dc  call    VfsAccessCheck
0x1400047e1  test    eax, eax
0x1400047e3  js      loc_140004995
0x1400047e9  mov     eax, [rbx+4Ch]
0x1400047ec  test    al, 10h
0x1400047ee  jnz     loc_14000488D
0x1400047f4  mov     rcx, [rbx+30h]; Instance
0x1400047f8  lea     rdx, [rsp+0A8h+Context]; Context
0x140004800  mov     [rsp+0A8h+Context], 0
0x14000480c  call    cs:__imp_FltGetInstanceContext
0x140004813  nop     dword ptr [rax+rax+00h]
0x140004818  mov     ebp, eax
0x14000481a  test    eax, eax
0x14000481c  jns     short loc_14000483E
0x14000481e  mov     r9, [rbx+30h]
0x140004822  lea     r8, aVfscreateforcr_0; "VfsCreateForCreate() - Failed to get in"...
0x140004829  xor     edx, edx
0x14000482b  mov     dword ptr [rsp+0A8h+var_88], ebp
0x14000482f  lea     ecx, [rdx+1]
0x140004832  call    LogWrite
0x140004837  mov     eax, ebp
0x140004839  jmp     loc_140004995
0x14000483e  mov     rax, [rsp+0A8h+Context]
0x140004846  lea     r14, [rbx+38h]
0x14000484a  mov     r8, [rbx+10h]
0x14000484e  mov     r9, r14
0x140004851  mov     rdx, [rbx+30h]
0x140004855  movzx   ecx, word ptr [rax+8]
0x140004859  mov     word ptr [rsp+0A8h+var_88], cx
0x14000485e  mov     rcx, [rbx+18h]
0x140004862  call    VfsCreateParentDirectories
0x140004867  mov     rcx, [rsp+0A8h+Context]; Context
0x14000486f  mov     ebp, eax
0x140004871  call    cs:__imp_FltReleaseContext
0x140004878  nop     dword ptr [rax+rax+00h]
0x14000487d  test    ebp, ebp
0x14000487f  jns     short loc_140004891
0x140004881  mov     r9, r14
0x140004884  lea     r8, aVfscreateforcr; "VfsCreateForCreate() - Failed to create"...
0x14000488b  jmp     short loc_140004829
0x14000488d  lea     r14, [rbx+38h]
0x140004891  test    r12b, r12b
0x140004894  jz      short loc_1400048C6
0x140004896  mov     rcx, [rdi+10h]
0x14000489a  movzx   r8d, word ptr [r14]; FileNameLength
0x14000489e  mov     rdx, [r14+8]; NewFileName
0x1400048a2  mov     rcx, [rcx+8]; FileObject
0x1400048a6  call    cs:__imp_IoReplaceFileObjectName
0x1400048ad  nop     dword ptr [rax+rax+00h]
0x1400048b2  test    eax, eax
0x1400048b4  js      loc_140004995
0x1400048ba  mov     dword ptr [r15], 2
0x1400048c1  jmp     loc_140004993
0x1400048c6  mov     r8d, [rbx+4Ch]
0x1400048ca  lea     rax, [rsp+0A8h+arg_8]
0x1400048d2  mov     [rsp+0A8h+var_30], rax; __int64
0x1400048d7  mov     ecx, r8d
0x1400048da  mov     rax, [rbx+10h]
0x1400048de  mov     edx, r8d
0x1400048e1  mov     [rsp+0A8h+var_38], rax; __int64
0x1400048e6  xor     r9d, r9d
0x1400048e9  mov     rax, [rbx+8]
0x1400048ed  mov     [rsp+0A8h+var_40], rax; __int64
0x1400048f2  mov     rax, [rbx]
0x1400048f5  mov     [rsp+0A8h+var_48], rax; __int64
0x1400048fa  mov     rax, [rbx+30h]
0x1400048fe  mov     [rsp+0A8h+var_50], 0; char
0x140004903  shr     edx, 0Dh
0x140004906  shr     ecx, 9
0x140004909  and     dl, 1
0x14000490c  mov     [rsp+0A8h+var_58], dl; char
0x140004910  and     cl, 1
0x140004913  mov     [rsp+0A8h+var_60], cl; char
0x140004917  lea     edx, [r9+2]
0x14000491b  shr     r8d, 6
0x14000491f  mov     rcx, rdi; CallbackData
0x140004922  and     r8b, 1
0x140004926  mov     [rsp+0A8h+var_68], r8b; char
0x14000492b  xor     r8d, r8d
0x14000492e  mov     [rsp+0A8h+var_70], 0; char
0x140004933  mov     [rsp+0A8h+var_78], r14; __int64
0x140004938  mov     [rsp+0A8h+TargetInstance], rax; TargetInstance
0x14000493d  mov     [rsp+0A8h+var_88], 0; PFLT_INSTANCE
0x140004946  call    VfsCreateShadow
0x14000494b  test    eax, eax
0x14000494d  js      short loc_140004995
0x14000494f  mov     rax, [rdi+10h]
0x140004953  mov     rcx, [rax+18h]
0x140004957  mov     rdx, [rcx+8]
0x14000495b  mov     eax, [rdx+10h]
0x14000495e  or      [rdx+14h], eax
0x140004961  mov     eax, [rdx+14h]
0x140004964  bt      eax, 19h
0x140004968  jnb     short loc_140004976
0x14000496a  btr     eax, 19h
0x14000496e  or      eax, 1F01FFh
0x140004973  mov     [rdx+14h], eax
0x140004976  mov     dword ptr [rdx+10h], 0
0x14000497d  mov     qword ptr [rdi+20h], 2
0x140004985  mov     dword ptr [rdi+18h], 0
0x14000498c  mov     dword ptr [r15], 3
0x140004993  xor     eax, eax
0x140004995  mov     rbx, [rsp+0A8h+arg_0]
0x14000499d  add     rsp, 80h
0x1400049a4  pop     r15
0x1400049a6  pop     r14
0x1400049a8  pop     r12
0x1400049aa  pop     rdi
0x1400049ab  pop     rbp
0x1400049ac  retn
```
