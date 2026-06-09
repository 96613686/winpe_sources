# CBdeCfgConsole::GetStepDescription(_BDECFG_STEP_ID,ushort * *)

- ea: `0x140002480`
- end: `0x140002725`
- name: `?GetStepDescription@CBdeCfgConsole@@AEAAJW4_BDECFG_STEP_ID@@PEAPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(CBdeCfgConsole *, int, _QWORD *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140002a00`
- `0x140004010`

## callees

- `0x140001008`
- `0x1400013c8`
- `0x140002480`
- `0x14000272c`
- `0x1400027a4`
- `0x1400027f0`
- `0x140004460`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000258b`
- `KERNEL32!FormatMessageW` at `0x14000258b`
- `KERNEL32!LocalFree` at `0x1400026f4`
- `KERNEL32!LocalFree` at `0x14000468a`
- `KERNEL32!LocalFree` at `0x1400026f4`
- `KERNEL32!LocalFree` at `0x14000468a`
- `KERNEL32!GetLastError` at `0x140002595`
- `KERNEL32!GetLastError` at `0x140002595`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000254b`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000254b`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetStepDescription(CBdeCfgConsole *a1, int a2, _QWORD *a3, unsigned __int64 *a4)
{
  void *v5; // rsi
  signed int ResourceString; // ebx
  int v7; // edx
  signed int StepTemplateShrinking; // eax
  DWORD v9; // eax
  signed int LastError; // eax
  unsigned __int64 v11; // rdi
  size_t v12; // rax
  _WORD *v13; // rax
  __int16 *v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // rcx
  __int64 v17; // rax
  __int16 v18; // r9
  unsigned int v20; // [rsp+44h] [rbp-94h] BYREF
  signed int v21; // [rsp+48h] [rbp-90h]
  LPCVOID lpSource; // [rsp+50h] [rbp-88h] BYREF
  WCHAR Buffer[4]; // [rsp+58h] [rbp-80h] BYREF
  _WORD *v24; // [rsp+60h] [rbp-78h]
  _WORD *v25; // [rsp+68h] [rbp-70h]
  __int64 v26; // [rsp+70h] [rbp-68h]
  __int16 *v27; // [rsp+78h] [rbp-60h]
  unsigned __int64 v28; // [rsp+80h] [rbp-58h]
  __int64 v29; // [rsp+88h] [rbp-50h]
  _OWORD Arguments[2]; // [rsp+90h] [rbp-48h] BYREF

  lpSource = 0;
  v5 = 0;
  v24 = 0;
  *(_QWORD *)Buffer = 0;
  memset(Arguments, 0, sizeof(Arguments));
  v20 = 0;
  *a3 = 0;
  if ( !*((_BYTE *)a1 + 72) )
  {
    ResourceString = -1063256037;
    goto LABEL_37;
  }
  if ( !a2 )
  {
    StepTemplateShrinking = CBdeCfgConsole::GetStepTemplateShrinking(a1, 0, &v20, (unsigned __int64 *)Arguments);
    goto LABEL_11;
  }
  v7 = a2 - 1;
  if ( !v7 )
  {
    StepTemplateShrinking = CBdeCfgConsole::GetStepTemplateCreating(a1, 0, &v20, (unsigned __int64 *)Arguments);
    goto LABEL_11;
  }
  if ( v7 == 1 )
  {
    StepTemplateShrinking = CBdeCfgConsole::GetStepTemplateMigrating(a1, 1u, &v20, a4);
LABEL_11:
    ResourceString = StepTemplateShrinking;
    goto LABEL_12;
  }
  ResourceString = -1063256037;
LABEL_12:
  if ( ResourceString >= 0 )
  {
    ResourceString = BdeCfgLoadResourceString(v20, (unsigned __int16 **)&lpSource);
    if ( ResourceString >= 0 )
    {
      v9 = FormatMessageW(0x2500u, lpSource, 0, 0, Buffer, 0, (va_list *)Arguments);
      if ( v9 )
      {
        v11 = v9 + 1;
        v12 = 2 * v11;
        if ( !is_mul_ok(v11, 2u) )
          v12 = -1;
        v13 = operator new(v12, (const struct std::nothrow_t *)std::nothrow);
        v5 = v13;
        v24 = v13;
        if ( v13 )
        {
          v14 = *(__int16 **)Buffer;
          v21 = 0;
          if ( !v11 || (ResourceString = 0, v11 > 0x7FFFFFFF) )
            ResourceString = -2147024809;
          v21 = ResourceString;
          if ( ResourceString < 0 )
          {
            if ( v11 )
              *v13 = 0;
          }
          else
          {
            v15 = 2147483646;
            v29 = 2147483646;
            v27 = *(__int16 **)Buffer;
            v28 = v11;
            v16 = v13;
            v25 = v13;
            ResourceString = 0;
            v17 = 0;
            v26 = 0;
            while ( v11 )
            {
              if ( !v15 )
                goto LABEL_32;
              v18 = *v14;
              if ( !*v14 )
                goto LABEL_32;
              v27 = ++v14;
              *v16++ = v18;
              v25 = v16;
              v28 = --v11;
              v29 = --v15;
              v26 = ++v17;
            }
            v25 = --v16;
            v26 = v17 - 1;
            ResourceString = -2147024774;
LABEL_32:
            *v16 = 0;
            v21 = ResourceString;
          }
          if ( ResourceString >= 0 )
          {
            *a3 = v5;
            v5 = 0;
            v24 = 0;
          }
        }
        else
        {
          ResourceString = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        ResourceString = LastError;
        if ( LastError > 0 )
          ResourceString = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
LABEL_37:
  operator delete((void *)lpSource);
  operator delete(v5);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140002480  mov     r11, rsp
0x140002483  mov     [r11+10h], rbx
0x140002487  mov     [r11+20h], rsi
0x14000248b  push    rdi
0x14000248c  push    r14
0x14000248e  push    r15
0x140002490  sub     rsp, 0C0h
0x140002497  mov     rax, cs:__security_cookie
0x14000249e  xor     rax, rsp
0x1400024a1  mov     [rsp+0D8h+var_28], rax
0x1400024a9  mov     r14, r8
0x1400024ac  xor     r15d, r15d
0x1400024af  mov     [rsp+0D8h+lpSource], r15
0x1400024b4  mov     esi, r15d
0x1400024b7  mov     [r11-78h], r15
0x1400024bb  mov     [r11-80h], r15
0x1400024bf  xorps   xmm0, xmm0
0x1400024c2  movups  xmmword ptr [r11-48h], xmm0
0x1400024c7  movups  xmmword ptr [r11-38h], xmm0
0x1400024cc  mov     [rsp+0D8h+var_94], r15d
0x1400024d1  mov     [r8], r15
0x1400024d4  mov     al, [rcx+48h]
0x1400024d7  test    al, al
0x1400024d9  jnz     short loc_1400024E9
0x1400024db  mov     ebx, 0C0A0001Bh
0x1400024e0  mov     [rsp+0D8h+var_98], ebx
0x1400024e4  jmp     loc_1400026D8
0x1400024e9  test    edx, edx
0x1400024eb  jz      short loc_140002522
0x1400024ed  sub     edx, 1; unsigned int
0x1400024f0  jz      short loc_14000250E
0x1400024f2  cmp     edx, 1
0x1400024f5  jz      short loc_140002502
0x1400024f7  mov     ebx, 0C0A0001Bh
0x1400024fc  mov     [rsp+0D8h+var_98], ebx
0x140002500  jmp     short loc_14000253A
0x140002502  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x140002507  call    ?GetStepTemplateMigrating@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetStepTemplateMigrating(ulong,ulong *,unsigned __int64 *)
0x14000250c  jmp     short loc_140002534
0x14000250e  lea     r9, [rsp+0D8h+var_48]; unsigned __int64 *
0x140002516  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x14000251b  call    ?GetStepTemplateCreating@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetStepTemplateCreating(ulong,ulong *,unsigned __int64 *)
0x140002520  jmp     short loc_140002534
0x140002522  lea     r9, [rsp+0D8h+var_48]; unsigned __int64 *
0x14000252a  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x14000252f  call    ?GetStepTemplateShrinking@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetStepTemplateShrinking(ulong,ulong *,unsigned __int64 *)
0x140002534  mov     ebx, eax
0x140002536  mov     [rsp+0D8h+var_98], eax
0x14000253a  test    ebx, ebx
0x14000253c  js      loc_1400026D8
0x140002542  lea     rdx, [rsp+0D8h+lpSource]
0x140002547  mov     ecx, [rsp+0D8h+var_94]
0x14000254b  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140002551  mov     ebx, eax
0x140002553  mov     [rsp+0D8h+var_98], eax
0x140002557  test    eax, eax
0x140002559  js      loc_1400026D8
0x14000255f  lea     rax, [rsp+0D8h+var_48]
0x140002567  mov     [rsp+0D8h+Arguments], rax; Arguments
0x14000256c  mov     [rsp+0D8h+nSize], r15d; nSize
0x140002571  lea     rax, [rsp+0D8h+Buffer]
0x140002576  mov     [rsp+0D8h+lpBuffer], rax; lpBuffer
0x14000257b  xor     r9d, r9d; dwLanguageId
0x14000257e  xor     r8d, r8d; dwMessageId
0x140002581  mov     rdx, [rsp+0D8h+lpSource]; lpSource
0x140002586  mov     ecx, 2500h; dwFlags
0x14000258b  call    cs:__imp_FormatMessageW
0x140002591  test    eax, eax
0x140002593  jnz     short loc_1400025B3
0x140002595  call    cs:__imp_GetLastError
0x14000259b  mov     ebx, eax
0x14000259d  test    eax, eax
0x14000259f  jle     loc_1400024E0
0x1400025a5  movzx   ebx, ax
0x1400025a8  or      ebx, 80070000h
0x1400025ae  jmp     loc_1400024E0
0x1400025b3  lea     edi, [rax+1]
0x1400025b6  mov     eax, 2
0x1400025bb  mul     rdi
0x1400025be  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400025c5  cmovb   rax, rcx
0x1400025c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400025d0  mov     rcx, rax; unsigned __int64
0x1400025d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400025d8  mov     rsi, rax
0x1400025db  mov     [rsp+0D8h+var_78], rax
0x1400025e0  test    rax, rax
0x1400025e3  jnz     short loc_1400025EF
0x1400025e5  mov     ebx, 8007000Eh
0x1400025ea  jmp     loc_1400024E0
0x1400025ef  mov     rdx, qword ptr [rsp+0D8h+Buffer]
0x1400025f4  mov     [rsp+0D8h+var_90], r15d
0x1400025f9  test    rdi, rdi
0x1400025fc  jz      short loc_14000260A
0x1400025fe  mov     ebx, r15d
0x140002601  cmp     rdi, 7FFFFFFFh
0x140002608  jbe     short loc_14000260F
0x14000260a  mov     ebx, 80070057h
0x14000260f  mov     [rsp+0D8h+var_90], ebx
0x140002613  test    ebx, ebx
0x140002615  js      loc_1400026BA
0x14000261b  mov     r8d, 7FFFFFFEh
0x140002621  mov     [rsp+0D8h+var_50], r8
0x140002629  mov     [rsp+0D8h+var_60], rdx
0x14000262e  mov     [rsp+0D8h+var_58], rdi
0x140002636  mov     rcx, rsi
0x140002639  mov     [rsp+0D8h+var_70], rcx
0x14000263e  mov     ebx, r15d
0x140002641  mov     rax, r15
0x140002644  mov     [rsp+0D8h+var_68], rax
0x140002649  test    rdi, rdi
0x14000264c  jz      short loc_140002698
0x14000264e  test    r8, r8
0x140002651  jz      short loc_140002693
0x140002653  movzx   r9d, word ptr [rdx]
0x140002657  test    r9w, r9w
0x14000265b  jz      short loc_140002693
0x14000265d  add     rdx, 2
0x140002661  mov     [rsp+0D8h+var_60], rdx
0x140002666  mov     [rcx], r9w
0x14000266a  add     rcx, 2
0x14000266e  mov     [rsp+0D8h+var_70], rcx
0x140002673  dec     rdi
0x140002676  mov     [rsp+0D8h+var_58], rdi
0x14000267e  dec     r8
0x140002681  mov     [rsp+0D8h+var_50], r8
0x140002689  inc     rax
0x14000268c  mov     [rsp+0D8h+var_68], rax
0x140002691  jmp     short loc_140002649
0x140002693  test    rdi, rdi
0x140002696  jnz     short loc_1400026AE
0x140002698  sub     rcx, 2
0x14000269c  mov     [rsp+0D8h+var_70], rcx
0x1400026a1  dec     rax
0x1400026a4  mov     [rsp+0D8h+var_68], rax
0x1400026a9  mov     ebx, 8007007Ah
0x1400026ae  mov     eax, r15d
0x1400026b1  mov     [rcx], ax
0x1400026b4  mov     [rsp+0D8h+var_90], ebx
0x1400026b8  jmp     short loc_1400026C5
0x1400026ba  test    rdi, rdi
0x1400026bd  jz      short loc_1400026C5
0x1400026bf  mov     eax, r15d
0x1400026c2  mov     [rsi], ax
0x1400026c5  mov     [rsp+0D8h+var_98], ebx
0x1400026c9  test    ebx, ebx
0x1400026cb  js      short loc_1400026D8
0x1400026cd  mov     [r14], rsi
0x1400026d0  mov     rsi, r15
0x1400026d3  mov     [rsp+0D8h+var_78], r15
0x1400026d8  mov     rcx, [rsp+0D8h+lpSource]; Block
0x1400026dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400026e2  mov     rcx, rsi; Block
0x1400026e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400026ea  mov     rcx, qword ptr [rsp+0D8h+Buffer]; hMem
0x1400026ef  test    rcx, rcx
0x1400026f2  jz      short loc_1400026FA
0x1400026f4  call    cs:__imp_LocalFree
0x1400026fa  mov     eax, ebx
0x1400026fc  mov     rcx, [rsp+0D8h+var_28]
0x140002704  xor     rcx, rsp; StackCookie
0x140002707  call    __security_check_cookie
0x14000270c  lea     r11, [rsp+0D8h+var_18]
0x140002714  mov     rbx, [r11+28h]
0x140002718  mov     rsi, [r11+38h]
0x14000271c  mov     rsp, r11
0x14000271f  pop     r15
0x140002721  pop     r14
0x140002723  pop     rdi
0x140002724  retn
0x140004666  push    rbp
0x140004668  sub     rsp, 40h
0x14000466c  mov     rbp, rdx
0x14000466f  mov     rcx, [rbp+50h]; Block
0x140004673  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004678  mov     rcx, [rbp+60h]; Block
0x14000467c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004681  mov     rcx, [rbp+58h]; hMem
0x140004685  test    rcx, rcx
0x140004688  jz      short loc_140004691
0x14000468a  call    cs:__imp_LocalFree
0x140004690  nop
0x140004691  add     rsp, 40h
0x140004695  pop     rbp
0x140004696  retn
```
