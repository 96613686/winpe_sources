# Streaming::FileOperations::CreateParentDirectories(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &)

- ea: `0x140002910`
- end: `0x140002a0b`
- name: `?CreateParentDirectories@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@2@Z`
- size: `251`
- prototype: `__int64 __fastcall(Streaming::FileOperations *this, struct _FLT_FILTER *, struct _FLT_INSTANCE *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007fe4`

## callees

- `0x140002864`
- `0x140002910`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400029bd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400029bd`
- `FLTMGR!FltClose` at `0x1400029d6`
- `FLTMGR!FltClose` at `0x1400029d6`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::CreateParentDirectories(
        Streaming::FileOperations *this,
        struct _FLT_FILTER *a2,
        struct _FLT_INSTANCE *a3,
        const struct _UNICODE_STRING *a4)
{
  USHORT Length; // bx
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // bx
  __int16 v10; // dx
  __int64 v12; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING v13; // [rsp+40h] [rbp-10h] BYREF
  PVOID Object; // [rsp+90h] [rbp+40h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp+48h] BYREF

  Length = a4->Length;
  v13.MaximumLength = *((_WORD *)a3 + 1);
  v13.Buffer = (PWSTR)*((_QWORD *)a3 + 1);
  v8 = *(_WORD *)a3;
  *(_DWORD *)(&v13.MaximumLength + 1) = 0;
  v13.Length = 0;
  v9 = Length >> 1;
  while ( ++v9 < (unsigned __int16)(v8 >> 1) )
  {
    v10 = *(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * v9);
    if ( !v10 )
      break;
    if ( v10 == 92 )
    {
      FileHandle = 0;
      Object = 0;
      v13.Length = 2 * v9;
      Streaming::FileOperations::CreateDirectoryInternal(
        this,
        a2,
        &v13,
        0x130116u,
        2u,
        v12,
        (PFILE_OBJECT *)&Object,
        &FileHandle);
      if ( Object )
      {
        ObfDereferenceObject(Object);
        Object = 0;
      }
      if ( FileHandle )
        FltClose(FileHandle);
    }
    v8 = *(_WORD *)a3;
  }
  return 0;
}

```

## disassembly

```asm
0x140002910  mov     [rsp-28h+arg_0], rbx
0x140002915  push    rbp
0x140002916  push    rsi
0x140002917  push    rdi
0x140002918  push    r14
0x14000291a  push    r15
0x14000291c  mov     rbp, rsp
0x14000291f  sub     rsp, 50h
0x140002923  movzx   eax, word ptr [r8+2]
0x140002928  xor     r15d, r15d
0x14000292b  movzx   ebx, word ptr [r9]
0x14000292f  mov     rdi, r8
0x140002932  mov     [rbp+var_E], ax
0x140002936  mov     rsi, rdx
0x140002939  mov     rax, [r8+8]
0x14000293d  mov     r14, rcx
0x140002940  mov     [rbp+var_8], rax
0x140002944  movzx   eax, word ptr [r8]
0x140002948  mov     [rbp+var_C], r15d
0x14000294c  mov     [rbp+var_10], r15w
0x140002951  shr     bx, 1
0x140002954  jmp     loc_1400029E5
0x140002959  mov     rax, [rdi+8]
0x14000295d  movzx   ecx, bx
0x140002960  movzx   edx, word ptr [rax+rcx*2]
0x140002964  test    dx, dx
0x140002967  jz      loc_1400029F4
0x14000296d  cmp     dx, 5Ch ; '\'
0x140002971  jnz     short loc_1400029E2
0x140002973  movzx   eax, bx
0x140002976  mov     [rbp+FileHandle], r15
0x14000297a  add     ax, ax
0x14000297d  mov     [rbp+Object], r15
0x140002981  mov     [rbp+var_10], ax
0x140002985  lea     r8, [rbp+var_10]
0x140002989  lea     rax, [rbp+FileHandle]
0x14000298d  mov     r9d, 130116h
0x140002993  mov     [rsp+50h+var_18], rax
0x140002998  mov     rdx, rsi
0x14000299b  lea     rax, [rbp+Object]
0x14000299f  mov     rcx, r14
0x1400029a2  mov     [rsp+50h+var_20], rax
0x1400029a7  mov     [rsp+50h+var_30], 2
0x1400029af  call    ?CreateDirectoryInternal@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KKPEAXAEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::CreateDirectoryInternal(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,ulong,ulong,void *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x1400029b4  mov     rcx, [rbp+Object]; Object
0x1400029b8  test    rcx, rcx
0x1400029bb  jz      short loc_1400029CD
0x1400029bd  call    cs:__imp_ObfDereferenceObject
0x1400029c4  nop     dword ptr [rax+rax+00h]
0x1400029c9  mov     [rbp+Object], r15
0x1400029cd  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400029d1  test    rcx, rcx
0x1400029d4  jz      short loc_1400029E2
0x1400029d6  call    cs:__imp_FltClose
0x1400029dd  nop     dword ptr [rax+rax+00h]
0x1400029e2  movzx   eax, word ptr [rdi]
0x1400029e5  inc     bx
0x1400029e8  shr     ax, 1
0x1400029eb  cmp     bx, ax
0x1400029ee  jb      loc_140002959
0x1400029f4  mov     rbx, [rsp+50h+arg_0]
0x1400029fc  xor     eax, eax
0x1400029fe  add     rsp, 50h
0x140002a02  pop     r15
0x140002a04  pop     r14
0x140002a06  pop     rdi
0x140002a07  pop     rsi
0x140002a08  pop     rbp
0x140002a09  retn
```
