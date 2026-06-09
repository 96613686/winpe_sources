# WofPreFsctlSetReparsePoint

- ea: `0x1400361b0`
- end: `0x140036375`
- name: `WofPreFsctlSetReparsePoint`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140034740`

## callees

- `0x14000a914`
- `0x140034fa0`
- `0x1400361b0`
- `0x140036954`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140036220`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140036238`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140036220`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140036238`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003632e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003632e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400362f7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400362f7`
- `FLTMGR!FltGetStreamContext` at `0x14003627b`
- `FLTMGR!FltGetStreamContext` at `0x14003627b`
- `FLTMGR!FltReleaseContext` at `0x1400362d0`
- `FLTMGR!FltReleaseContext` at `0x14003633e`
- `FLTMGR!FltReleaseContext` at `0x140036358`
- `FLTMGR!FltReleaseContext` at `0x1400362d0`
- `FLTMGR!FltReleaseContext` at `0x14003633e`
- `FLTMGR!FltReleaseContext` at `0x140036358`

## pseudocode

```c
__int64 __fastcall WofPreFsctlSetReparsePoint(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v6; // rdi
  NTSTATUS v7; // eax
  ULONG v9; // ecx
  _DWORD *v10; // rsi
  int v11; // ecx
  struct _FILE_OBJECT *v12; // rdx
  struct _FLT_INSTANCE *v13; // rcx
  int v14; // edi
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+20h] BYREF
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF

  v16 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  v6 = *(_QWORD *)(v3 + 48);
  if ( !v6 )
  {
    v7 = -1073741306;
LABEL_3:
    *(_DWORD *)(a1 + 24) = v7;
    return 4;
  }
  v9 = *(_DWORD *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 40) == 590860 )
  {
    if ( v9 < 0x20 )
    {
      v7 = -1073741789;
      goto LABEL_3;
    }
    v10 = (_DWORD *)(v6 + 32);
    v7 = FsRtlValidateReparsePointBuffer(v9 - 32, (PREPARSE_DATA_BUFFER)(v6 + 32));
    if ( v7 < 0 )
      goto LABEL_3;
    v11 = *(_DWORD *)(v6 + 4);
  }
  else
  {
    v7 = FsRtlValidateReparsePointBuffer(v9, *(PREPARSE_DATA_BUFFER *)(v3 + 48));
    if ( v7 < 0 )
      goto LABEL_3;
    v11 = 0;
    v10 = (_DWORD *)v6;
  }
  if ( *v10 == FileTag || v11 == FileTag )
  {
    *(_DWORD *)(a1 + 24) = -1073741811;
    return 4;
  }
  v12 = (struct _FILE_OBJECT *)a2[4];
  v13 = (struct _FLT_INSTANCE *)a2[3];
  Context = 0;
  LOBYTE(v16) = 0;
  if ( FltGetStreamContext(v13, v12, &Context) >= 0 )
  {
    if ( (int)WofIsDataInFilesystemEx(Context, a2, (bool *)&v16, 0) >= 0 && !(_BYTE)v16 )
    {
      v14 = WofEnsureExtdFileContext(*(_QWORD *)Context);
      if ( v14 >= 0 )
      {
        WofEnsureExtdFileContext(*(_QWORD *)Context);
        ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        if ( (*((_DWORD *)Context + 2) & 4) == 0 )
          v14 = WofInflateFile(a1, (__int64)a2, Context, 1);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        FltReleaseContext(Context);
        if ( v14 >= 0 )
          return 1;
      }
      else
      {
        FltReleaseContext(Context);
      }
      *(_DWORD *)(a1 + 24) = v14;
      return 4;
    }
    FltReleaseContext(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x1400361b0  mov     [rsp-18h+arg_8], rbx
0x1400361b5  mov     [rsp-18h+arg_18], rsi
0x1400361ba  mov     [rsp-18h+arg_10], r8
0x1400361bf  push    rbp
0x1400361c0  push    rdi
0x1400361c1  push    r14
0x1400361c3  mov     rbp, rsp
0x1400361c6  sub     rsp, 20h
0x1400361ca  mov     rax, [rcx+10h]
0x1400361ce  mov     r14, rdx
0x1400361d1  mov     rbx, rcx
0x1400361d4  mov     rdi, [rax+30h]
0x1400361d8  test    rdi, rdi
0x1400361db  jnz     short loc_1400361FE
0x1400361dd  mov     eax, 0C0000206h
0x1400361e2  mov     [rbx+18h], eax
0x1400361e5  mov     eax, 4
0x1400361ea  mov     rbx, [rsp+20h+arg_8]
0x1400361ef  mov     rsi, [rsp+20h+arg_18]
0x1400361f4  add     rsp, 20h
0x1400361f8  pop     r14
0x1400361fa  pop     rdi
0x1400361fb  pop     rbp
0x1400361fc  retn
0x1400361fe  cmp     dword ptr [rax+28h], 9040Ch
0x140036205  mov     ecx, [rax+20h]; BufferLength
0x140036208  jnz     short loc_140036235
0x14003620a  cmp     ecx, 20h ; ' '
0x14003620d  jnb     short loc_140036216
0x14003620f  mov     eax, 0C0000023h
0x140036214  jmp     short loc_1400361E2
0x140036216  lea     rsi, [rdi+20h]
0x14003621a  add     ecx, 0FFFFFFE0h; BufferLength
0x14003621d  mov     rdx, rsi; ReparseBuffer
0x140036220  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x140036227  nop     dword ptr [rax+rax+00h]
0x14003622c  test    eax, eax
0x14003622e  js      short loc_1400361E2
0x140036230  mov     ecx, [rdi+4]
0x140036233  jmp     short loc_14003624D
0x140036235  mov     rdx, rdi; ReparseBuffer
0x140036238  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x14003623f  nop     dword ptr [rax+rax+00h]
0x140036244  test    eax, eax
0x140036246  js      short loc_1400361E2
0x140036248  xor     ecx, ecx
0x14003624a  mov     rsi, rdi
0x14003624d  mov     edx, cs:FileTag
0x140036253  cmp     [rsi], edx
0x140036255  jz      loc_140036369
0x14003625b  cmp     ecx, edx
0x14003625d  jz      loc_140036369
0x140036263  mov     rdx, [r14+20h]; FileObject
0x140036267  lea     r8, [rbp+Context]; Context
0x14003626b  mov     rcx, [r14+18h]; Instance
0x14003626f  mov     [rbp+Context], 0
0x140036277  mov     byte ptr [rbp+arg_10], 0
0x14003627b  call    cs:__imp_FltGetStreamContext
0x140036282  nop     dword ptr [rax+rax+00h]
0x140036287  test    eax, eax
0x140036289  jns     short loc_140036295
0x14003628b  mov     eax, 1
0x140036290  jmp     loc_1400361EA
0x140036295  mov     rcx, [rbp+Context]
0x140036299  lea     r8, [rbp+arg_10]
0x14003629d  xor     r9d, r9d
0x1400362a0  mov     rdx, r14
0x1400362a3  call    WofIsDataInFilesystemEx
0x1400362a8  test    eax, eax
0x1400362aa  js      loc_140036354
0x1400362b0  cmp     byte ptr [rbp+arg_10], 0
0x1400362b4  jnz     loc_140036354
0x1400362ba  mov     rcx, [rbp+Context]
0x1400362be  mov     rcx, [rcx]
0x1400362c1  call    WofEnsureExtdFileContext
0x1400362c6  mov     rcx, [rbp+Context]; Context
0x1400362ca  mov     edi, eax
0x1400362cc  test    eax, eax
0x1400362ce  jns     short loc_1400362E4
0x1400362d0  call    cs:__imp_FltReleaseContext
0x1400362d7  nop     dword ptr [rax+rax+00h]
0x1400362dc  mov     [rbx+18h], edi
0x1400362df  jmp     loc_1400361E5
0x1400362e4  mov     rcx, [rcx]
0x1400362e7  call    WofEnsureExtdFileContext
0x1400362ec  mov     rax, [rbp+Context]
0x1400362f0  mov     rcx, [rax]
0x1400362f3  mov     rcx, [rcx+10h]; FastMutex
0x1400362f7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400362fe  nop     dword ptr [rax+rax+00h]
0x140036303  mov     rax, [rbp+Context]
0x140036307  mov     ecx, [rax+8]
0x14003630a  test    cl, 4
0x14003630d  jnz     short loc_140036323
0x14003630f  mov     r8, [rbp+Context]
0x140036313  mov     r9b, 1
0x140036316  mov     rdx, r14
0x140036319  mov     rcx, rbx
0x14003631c  call    WofInflateFile
0x140036321  mov     edi, eax
0x140036323  mov     rax, [rbp+Context]
0x140036327  mov     rcx, [rax]
0x14003632a  mov     rcx, [rcx+10h]; FastMutex
0x14003632e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036335  nop     dword ptr [rax+rax+00h]
0x14003633a  mov     rcx, [rbp+Context]; Context
0x14003633e  call    cs:__imp_FltReleaseContext
0x140036345  nop     dword ptr [rax+rax+00h]
0x14003634a  test    edi, edi
0x14003634c  jns     loc_14003628B
0x140036352  jmp     short loc_1400362DC
0x140036354  mov     rcx, [rbp+Context]; Context
0x140036358  call    cs:__imp_FltReleaseContext
0x14003635f  nop     dword ptr [rax+rax+00h]
0x140036364  jmp     loc_14003628B
0x140036369  mov     dword ptr [rbx+18h], 0C000000Dh
0x140036370  jmp     loc_1400361E5
```
