# VfsCreateForOverwrite

- ea: `0x14000502c`
- end: `0x140005301`
- name: `VfsCreateForOverwrite`
- size: `725`
- prototype: `int __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003c00`

## callees

- `0x140002b4c`
- `0x14000437c`
- `0x14000502c`
- `0x14000e438`
- `0x14000eb14`

## import_xrefs

- `ntoskrnl!IoReplaceFileObjectName` at `0x140005208`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140005208`

## pseudocode

```c
int __fastcall VfsCreateForOverwrite(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _DWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int Options; // r13d
  int v8; // eax
  int result; // eax
  bool v10; // bp
  PFLT_IO_PARAMETER_BLOCK v11; // rcx
  int v12; // r8d
  __int64 v13; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  PACCESS_STATE AccessState; // r14
  int v16; // esi
  int v17; // r15d
  void *v18; // rcx
  struct _FLT_INSTANCE *v19; // r11
  __int64 v20; // [rsp+D0h] [rbp+8h] BYREF

  Iopb = CallbackData->Iopb;
  LOBYTE(v20) = 0;
  Options = Iopb->Parameters.Create.Options;
  *a3 = 0;
  v8 = *(_DWORD *)(a2 + 76);
  if ( (v8 & 0x200) != 0 || (v8 & 0x40) == 0 && (v8 & 0x80u) == 0 )
    return -1073741772;
  if ( (v8 & 4) != 0 )
    return (*(_DWORD *)(a2 + 76) & 0x40) != 0 ? -1073741790 : -1073741772;
  v10 = 0;
  if ( (v8 & 0x800) == 0 && (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x10000) == 0 )
    v10 = *(_QWORD *)(a2 + 24) == *(_QWORD *)(a2 + 48);
  if ( (v8 & 0x80) == 0 )
  {
    v11 = CallbackData->Iopb;
    v12 = *(_DWORD *)(a2 + 72);
    v13 = *(_QWORD *)(a2 + 16);
    SecurityContext = v11->Parameters.Create.SecurityContext;
    AccessState = SecurityContext->AccessState;
    v16 = ~SecurityContext->DesiredAccess & (v11->Parameters.Create.Options < 0x1000000 ? 65808 : 274);
    v17 = v16 | SecurityContext->DesiredAccess;
    if ( (AccessState->Flags & 4) != 0 )
      AccessState->PreviouslyGrantedAccess |= v16;
    if ( v12 )
      v18 = *(void **)(v13 + 80);
    else
      v18 = *(void **)(v13 + 72);
    result = VfsAccessCheck(v18, (__int64)CallbackData, v17, 0);
    if ( (v17 & 0x2000000) == 0 )
      AccessState->PreviouslyGrantedAccess &= ~v16;
    if ( result < 0 )
      return result;
    result = VfsCreateContextNormalize(a2);
    if ( result < 0 )
      return result;
    *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) |= v16;
    result = VfsCowCopyFile(
               a2 + 56,
               (__int64)CallbackData,
               *(struct _FLT_INSTANCE **)(a2 + 24),
               (struct _UNICODE_STRING *)(a2 + 32),
               *(PFLT_INSTANCE *)(a2 + 48),
               a2 + 56,
               *(_QWORD *)(a2 + 8),
               *(PVOID *)a2,
               (*(_DWORD *)(a2 + 76) & 0x10) == 0,
               0);
    *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) &= ~v16;
    if ( result < 0 )
      return result;
    *(_DWORD *)(a2 + 76) |= 0x90u;
    if ( (*(_DWORD *)(a2 + 76) & 0x800) == 0 )
      v10 = (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x10000) == 0
         && *(_QWORD *)(a2 + 24) == *(_QWORD *)(a2 + 48);
  }
  if ( v10 )
  {
    result = IoReplaceFileObjectName(CallbackData->Iopb->TargetFileObject, *(PWSTR *)(a2 + 64), *(_WORD *)(a2 + 56));
    if ( result < 0 )
      return result;
    *a3 = 2;
    return 0;
  }
  if ( (*(_DWORD *)(a2 + 76) & 0x800) != 0 )
    v19 = *(struct _FLT_INSTANCE **)(a2 + 24);
  else
    v19 = 0;
  result = VfsCreateShadow(
             CallbackData,
             Options >= 0x1000000 ? 4 : 0,
             v19,
             (struct _FLT_INSTANCE *)((a2 + 32) & -(__int64)((*(_DWORD *)(a2 + 76) & 0x800) != 0)),
             0,
             *(PFLT_INSTANCE *)(a2 + 48),
             a2 + 56,
             0,
             (*(_DWORD *)(a2 + 76) & 0x40) != 0,
             0,
             0,
             0,
             *(_QWORD *)a2,
             *(_QWORD *)(a2 + 8),
             *(_QWORD *)(a2 + 16),
             &v20);
  if ( result >= 0 )
  {
    CallbackData->IoStatus.Status = 0;
    CallbackData->IoStatus.Information = Options >= 0x1000000 ? 3 : 0;
    *a3 = 3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000502c  mov     r11, rsp
0x14000502f  push    rbx
0x140005030  push    rbp
0x140005031  push    rsi
0x140005032  push    rdi
0x140005033  push    r12
0x140005035  push    r13
0x140005037  push    r14
0x140005039  push    r15
0x14000503b  sub     rsp, 88h
0x140005042  mov     rax, [rcx+10h]
0x140005046  xor     r14d, r14d
0x140005049  mov     r12, r8
0x14000504c  mov     [r11+8], r14b
0x140005050  mov     rbx, rdx
0x140005053  mov     rdi, rcx
0x140005056  mov     r13d, [rax+20h]
0x14000505a  mov     [r8], r14d
0x14000505d  mov     eax, [rdx+4Ch]
0x140005060  bt      eax, 9
0x140005064  jnb     short loc_140005070
0x140005066  mov     eax, 0C0000034h
0x14000506b  jmp     loc_1400052EC
0x140005070  mov     ecx, eax
0x140005072  and     ecx, 40h
0x140005075  jnz     short loc_14000507B
0x140005077  test    al, al
0x140005079  jns     short loc_140005066
0x14000507b  test    al, 4
0x14000507d  jz      short loc_140005092
0x14000507f  neg     ecx
0x140005081  mov     eax, 0C0000034h
0x140005086  sbb     ecx, ecx
0x140005088  and     ecx, 0FFFFFFEEh
0x14000508b  add     eax, ecx
0x14000508d  jmp     loc_1400052EC
0x140005092  mov     edx, eax
0x140005094  mov     r9d, 800h
0x14000509a  and     edx, 80h
0x1400050a0  mov     bpl, r14b
0x1400050a3  test    r9d, eax
0x1400050a6  jnz     short loc_1400050C5
0x1400050a8  mov     rax, [rdi+10h]
0x1400050ac  mov     rcx, [rax+18h]
0x1400050b0  test    dword ptr [rcx+10h], 10000h
0x1400050b7  jnz     short loc_1400050C5
0x1400050b9  mov     rax, [rbx+30h]
0x1400050bd  cmp     [rbx+18h], rax
0x1400050c1  setz    bpl
0x1400050c5  test    edx, edx
0x1400050c7  jnz     loc_1400051F2
0x1400050cd  mov     rcx, [rdi+10h]
0x1400050d1  mov     r8d, [rbx+48h]
0x1400050d5  mov     rdx, [rbx+10h]
0x1400050d9  mov     rax, [rcx+18h]
0x1400050dd  cmp     dword ptr [rcx+20h], 1000000h
0x1400050e4  sbb     esi, esi
0x1400050e6  mov     r15d, [rax+10h]
0x1400050ea  and     esi, 0FFFEh
0x1400050f0  mov     r14, [rax+8]
0x1400050f4  add     esi, 112h
0x1400050fa  mov     eax, r15d
0x1400050fd  not     eax
0x1400050ff  and     esi, eax
0x140005101  mov     eax, [r14+0Ch]
0x140005105  or      r15d, esi
0x140005108  test    al, 4
0x14000510a  jz      short loc_140005110
0x14000510c  or      [r14+14h], esi
0x140005110  test    r8d, r8d
0x140005113  jnz     short loc_14000511B
0x140005115  mov     rcx, [rdx+48h]
0x140005119  jmp     short loc_14000511F
0x14000511b  mov     rcx, [rdx+50h]; SecurityDescriptor
0x14000511f  xor     r9d, r9d
0x140005122  mov     r8d, r15d
0x140005125  mov     rdx, rdi
0x140005128  call    VfsAccessCheck
0x14000512d  bt      r15d, 19h
0x140005132  jb      short loc_14000513C
0x140005134  mov     ecx, esi
0x140005136  not     ecx
0x140005138  and     [r14+14h], ecx
0x14000513c  xor     r14d, r14d
0x14000513f  test    eax, eax
0x140005141  js      loc_1400052EC
0x140005147  mov     rcx, rbx
0x14000514a  call    VfsCreateContextNormalize
0x14000514f  test    eax, eax
0x140005151  js      loc_1400052EC
0x140005157  mov     rax, [rdi+10h]
0x14000515b  lea     r9, [rbx+20h]
0x14000515f  mov     [rsp+0C8h+var_80], r14b
0x140005164  mov     rdx, rdi
0x140005167  mov     rcx, [rax+18h]
0x14000516b  or      [rcx+10h], esi
0x14000516e  lea     rcx, [rbx+38h]
0x140005172  mov     eax, [rbx+4Ch]
0x140005175  mov     r8, [rbx+18h]
0x140005179  shr     eax, 4
0x14000517c  not     al
0x14000517e  and     al, 1
0x140005180  mov     [rsp+0C8h+var_88], al
0x140005184  mov     rax, [rbx]
0x140005187  mov     qword ptr [rsp+0C8h+var_90], rax
0x14000518c  mov     rax, [rbx+8]
0x140005190  mov     [rsp+0C8h+var_98], rax
0x140005195  mov     rax, [rbx+30h]
0x140005199  mov     [rsp+0C8h+TargetInstance], rcx
0x14000519e  mov     [rsp+0C8h+var_A8], rax
0x1400051a3  call    VfsCowCopyFile
0x1400051a8  mov     rcx, [rdi+10h]
0x1400051ac  not     esi
0x1400051ae  mov     rdx, [rcx+18h]
0x1400051b2  and     [rdx+10h], esi
0x1400051b5  test    eax, eax
0x1400051b7  js      loc_1400052EC
0x1400051bd  or      dword ptr [rbx+4Ch], 90h
0x1400051c4  mov     r9d, 800h
0x1400051ca  test    [rbx+4Ch], r9d
0x1400051ce  jnz     short loc_1400051F2
0x1400051d0  mov     rax, [rdi+10h]
0x1400051d4  mov     rcx, [rax+18h]
0x1400051d8  test    dword ptr [rcx+10h], 10000h
0x1400051df  jz      short loc_1400051E6
0x1400051e1  mov     bpl, r14b
0x1400051e4  jmp     short loc_1400051F2
0x1400051e6  mov     rax, [rbx+30h]
0x1400051ea  cmp     [rbx+18h], rax
0x1400051ee  setz    bpl
0x1400051f2  test    bpl, bpl
0x1400051f5  jz      short loc_140005229
0x1400051f7  mov     rcx, [rdi+10h]
0x1400051fb  movzx   r8d, word ptr [rbx+38h]; FileNameLength
0x140005200  mov     rdx, [rbx+40h]; NewFileName
0x140005204  mov     rcx, [rcx+8]; FileObject
0x140005208  call    cs:__imp_IoReplaceFileObjectName
0x14000520f  nop     dword ptr [rax+rax+00h]
0x140005214  test    eax, eax
0x140005216  js      loc_1400052EC
0x14000521c  mov     dword ptr [r12], 2
0x140005224  jmp     loc_1400052EA
0x140005229  mov     edx, [rbx+4Ch]
0x14000522c  lea     rcx, [rbx+20h]
0x140005230  mov     r8d, edx
0x140005233  and     edx, r9d
0x140005236  and     r8d, 40h
0x14000523a  mov     eax, edx
0x14000523c  neg     eax
0x14000523e  sbb     r9, r9
0x140005241  and     r9, rcx
0x140005244  test    edx, edx
0x140005246  jz      short loc_14000524E
0x140005248  mov     r11, [rbx+18h]
0x14000524c  jmp     short loc_140005251
0x14000524e  mov     r11, r14
0x140005251  test    r8d, r8d
0x140005254  lea     rax, [rsp+0C8h+arg_0]
0x14000525c  mov     [rsp+0C8h+var_50], rax; __int64
0x140005261  lea     r10, [rbx+38h]
0x140005265  mov     rax, [rbx+10h]
0x140005269  setnz   cl
0x14000526c  mov     [rsp+0C8h+var_58], rax; __int64
0x140005271  cmp     r13d, 1000000h
0x140005278  mov     rax, [rbx+8]
0x14000527c  mov     r8, r11
0x14000527f  mov     [rsp+0C8h+var_60], rax; __int64
0x140005284  sbb     edx, edx
0x140005286  mov     rax, [rbx]
0x140005289  not     edx
0x14000528b  mov     [rsp+0C8h+var_68], rax; __int64
0x140005290  and     edx, 4
0x140005293  mov     rax, [rbx+30h]
0x140005297  mov     [rsp+0C8h+var_70], r14b; char
0x14000529c  mov     [rsp+0C8h+var_78], r14b; char
0x1400052a1  mov     [rsp+0C8h+var_80], r14b; char
0x1400052a6  mov     [rsp+0C8h+var_88], cl; char
0x1400052aa  mov     rcx, rdi; CallbackData
0x1400052ad  mov     [rsp+0C8h+var_90], r14b; char
0x1400052b2  mov     [rsp+0C8h+var_98], r10; __int64
0x1400052b7  mov     [rsp+0C8h+TargetInstance], rax; TargetInstance
0x1400052bc  mov     [rsp+0C8h+var_A8], r14; PFLT_INSTANCE
0x1400052c1  call    VfsCreateShadow
0x1400052c6  test    eax, eax
0x1400052c8  js      short loc_1400052EC
0x1400052ca  cmp     r13d, 1000000h
0x1400052d1  mov     [rdi+18h], r14d
0x1400052d5  sbb     rax, rax
0x1400052d8  not     rax
0x1400052db  and     eax, 3
0x1400052de  mov     [rdi+20h], rax
0x1400052e2  mov     dword ptr [r12], 3
0x1400052ea  xor     eax, eax
0x1400052ec  add     rsp, 88h
0x1400052f3  pop     r15
0x1400052f5  pop     r14
0x1400052f7  pop     r13
0x1400052f9  pop     r12
0x1400052fb  pop     rdi
0x1400052fc  pop     rsi
0x1400052fd  pop     rbp
0x1400052fe  pop     rbx
0x1400052ff  retn
```
