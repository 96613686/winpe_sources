# MpFsCtlQueryStreamInformation

- ea: `0x1400811e4`
- end: `0x140081307`
- name: `MpFsCtlQueryStreamInformation`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400448f0`

## callees

- `0x14000db48`
- `0x1400118d0`
- `0x140011900`
- `0x1400811e4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400812a9`
- `ntoskrnl!ProbeForWrite` at `0x1400812a9`
- `FLTMGR!FltReleaseContext` at `0x1400812da`
- `FLTMGR!FltReleaseContext` at `0x1400812da`
- `FLTMGR!FltGetStreamContext` at `0x140081224`
- `FLTMGR!FltGetStreamContext` at `0x140081224`

## pseudocode

```c
NTSTATUS __fastcall MpFsCtlQueryStreamInformation(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // edx
  __int64 v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // rbx
  volatile void *v11; // rdi
  __int64 Src; // [rsp+38h] [rbp-40h] BYREF
  int v13; // [rsp+40h] [rbp-38h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-30h] BYREF

  Src = 0;
  v13 = 0;
  Context = 0;
  result = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
  if ( result >= 0 )
  {
    v6 = *((_DWORD *)Context + 8);
    HIDWORD(Src) = v6;
    v7 = *((_DWORD *)Context + 12);
    v13 = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_dDZ(WPP_GLOBAL_Control->AttachedDevice, v7, v5, v6, v7, *(_QWORD *)(a2 + 32) + 88LL);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = *(_DWORD *)(v8 + 24);
    v10 = v9;
    if ( v9 > 0xC )
      v10 = 12;
    LODWORD(Src) = v10;
    v11 = *(volatile void **)(v8 + 56);
    ProbeForWrite(v11, v9, 4u);
    memmove((void *)v11, &Src, (unsigned int)v10);
    *(_QWORD *)(a1 + 32) = v10;
    FltReleaseContext(Context);
    return 0;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x1400811e4  mov     r11, rsp
0x1400811e7  mov     [r11+18h], rbx
0x1400811eb  push    rsi
0x1400811ec  push    rdi
0x1400811ed  push    r14
0x1400811ef  sub     rsp, 60h
0x1400811f3  mov     rax, cs:__security_cookie
0x1400811fa  xor     rax, rsp
0x1400811fd  mov     [rsp+78h+var_28], rax
0x140081202  mov     rbx, rdx
0x140081205  mov     r14, rcx
0x140081208  xor     eax, eax
0x14008120a  mov     [r11-40h], rax
0x14008120e  mov     [rsp+78h+var_38], eax
0x140081212  xor     esi, esi
0x140081214  mov     [r11-30h], rsi
0x140081218  lea     r8, [r11-30h]; Context
0x14008121c  mov     rdx, [rdx+20h]; FileObject
0x140081220  mov     rcx, [rbx+18h]; Instance
0x140081224  call    cs:__imp_FltGetStreamContext
0x14008122b  nop     dword ptr [rax+rax+00h]
0x140081230  test    eax, eax
0x140081232  jns     short loc_14008123C
0x140081234  lfence
0x140081237  jmp     loc_1400812E8
0x14008123c  mov     rax, [rsp+78h+Context]
0x140081241  mov     r9d, [rax+20h]
0x140081245  mov     [rsp+78h+var_3C], r9d
0x14008124a  mov     edx, [rax+30h]
0x14008124d  mov     [rsp+78h+var_38], edx
0x140081251  lea     rax, WPP_GLOBAL_Control
0x140081258  mov     rcx, cs:WPP_GLOBAL_Control
0x14008125f  cmp     rcx, rax
0x140081262  jz      short loc_140081285
0x140081264  mov     eax, [rcx+2Ch]
0x140081267  test    al, 4
0x140081269  jz      short loc_140081285
0x14008126b  mov     rax, [rbx+20h]
0x14008126f  add     rax, 58h ; 'X'
0x140081273  mov     [rsp+78h+var_50], rax
0x140081278  mov     [rsp+78h+var_58], edx
0x14008127c  mov     rcx, [rcx+18h]
0x140081280  call    WPP_SF_dDZ
0x140081285  mov     rdi, [r14+10h]
0x140081289  mov     eax, [rdi+18h]
0x14008128c  mov     ebx, eax
0x14008128e  mov     ecx, 0Ch
0x140081293  cmp     eax, ecx
0x140081295  cmova   ebx, ecx
0x140081298  mov     [rsp+78h+Src], ebx
0x14008129c  mov     rdi, [rdi+38h]
0x1400812a0  mov     edx, eax; Length
0x1400812a2  lea     r8d, [rcx-8]; Alignment
0x1400812a6  mov     rcx, rdi; Address
0x1400812a9  call    cs:__imp_ProbeForWrite
0x1400812b0  nop     dword ptr [rax+rax+00h]
0x1400812b5  mov     r8d, ebx; Size
0x1400812b8  lea     rdx, [rsp+78h+Src]; Src
0x1400812bd  mov     rcx, rdi; void *
0x1400812c0  call    memmove
0x1400812c5  mov     [r14+20h], rbx
0x1400812c9  mov     [rsp+78h+var_48], esi
0x1400812cd  jmp     short loc_1400812D5
0x1400812cf  mov     esi, eax
0x1400812d1  mov     [rsp+78h+var_48], eax
0x1400812d5  mov     rcx, [rsp+78h+Context]; Context
0x1400812da  call    cs:__imp_FltReleaseContext
0x1400812e1  nop     dword ptr [rax+rax+00h]
0x1400812e6  mov     eax, esi
0x1400812e8  mov     rcx, [rsp+78h+var_28]
0x1400812ed  xor     rcx, rsp; StackCookie
0x1400812f0  call    __security_check_cookie
0x1400812f5  mov     rbx, [rsp+78h+arg_10]
0x1400812fd  add     rsp, 60h
0x140081301  pop     r14
0x140081303  pop     rdi
0x140081304  pop     rsi
0x140081305  retn
```
