# CBdeCfgConsole::GetActionDescription(ushort * *)

- ea: `0x140002014`
- end: `0x1400022d0`
- name: `?GetActionDescription@CBdeCfgConsole@@AEAAJPEAPEAG@Z`
- size: `700`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140003554`

## callees

- `0x140001008`
- `0x1400013c8`
- `0x140002014`
- `0x1400022d8`
- `0x14000236c`
- `0x140002420`
- `0x140002480`
- `0x140004460`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000215d`
- `KERNEL32!FormatMessageW` at `0x14000215d`
- `KERNEL32!LocalFree` at `0x1400022c3`
- `KERNEL32!LocalFree` at `0x1400022c3`
- `KERNEL32!GetLastError` at `0x140002167`
- `KERNEL32!GetLastError` at `0x140002167`
- `BDEHDCFGLIB!?GetActionType@CDriveConfiguration@@QEAA?AW4BDECFG_ACTION_TYPE@@XZ` at `0x1400020a3`
- `BDEHDCFGLIB!?GetActionType@CDriveConfiguration@@QEAA?AW4BDECFG_ACTION_TYPE@@XZ` at `0x1400020a3`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000211d`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000211d`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::GetActionDescription(CBdeCfgConsole *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  int v6; // eax
  unsigned int v7; // edx
  int v8; // eax
  signed int ResourceString; // ebx
  signed int ActionTemplateUnallocatedSpace; // eax
  DWORD v11; // eax
  signed int LastError; // eax
  unsigned __int64 v13; // rdi
  size_t v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  unsigned __int16 *v18; // rcx
  __int64 v19; // rax
  unsigned __int16 v20; // r9
  unsigned int v21; // [rsp+44h] [rbp-94h] BYREF
  signed int v22; // [rsp+48h] [rbp-90h]
  LPCVOID lpSource; // [rsp+50h] [rbp-88h] BYREF
  WCHAR Buffer[4]; // [rsp+58h] [rbp-80h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-78h]
  unsigned __int16 *v26; // [rsp+68h] [rbp-70h]
  __int64 v27; // [rsp+70h] [rbp-68h]
  unsigned __int16 *v28; // [rsp+78h] [rbp-60h]
  unsigned __int64 v29; // [rsp+80h] [rbp-58h]
  __int64 v30; // [rsp+88h] [rbp-50h]
  _OWORD Arguments[2]; // [rsp+90h] [rbp-48h] BYREF

  lpSource = 0;
  v4 = 0;
  v25 = 0;
  *(_QWORD *)Buffer = 0;
  memset(Arguments, 0, sizeof(Arguments));
  v21 = 0;
  *a2 = 0;
  if ( !*((_BYTE *)this + 72) )
    return 3231711259LL;
  v6 = CDriveConfiguration::GetActionType() - 1;
  if ( v6 )
  {
    v8 = v6 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
        ResourceString = -1063256037;
        goto LABEL_11;
      }
      ActionTemplateUnallocatedSpace = CBdeCfgConsole::GetActionTemplateUnallocatedSpace(
                                         this,
                                         v7,
                                         &v21,
                                         (unsigned __int64 *)Arguments);
    }
    else
    {
      ActionTemplateUnallocatedSpace = CBdeCfgConsole::GetActionTemplateMerge(
                                         this,
                                         v7,
                                         &v21,
                                         (unsigned __int64 *)Arguments);
    }
  }
  else
  {
    ActionTemplateUnallocatedSpace = CBdeCfgConsole::GetActionTemplateSplit(
                                       this,
                                       v7,
                                       &v21,
                                       (unsigned __int64 *)Arguments);
  }
  ResourceString = ActionTemplateUnallocatedSpace;
LABEL_11:
  if ( ResourceString >= 0 )
  {
    ResourceString = BdeCfgLoadResourceString(v21, (unsigned __int16 **)&lpSource);
    if ( ResourceString >= 0 )
    {
      v11 = FormatMessageW(0x2500u, lpSource, 0, 0, Buffer, 0, (va_list *)Arguments);
      if ( v11 )
      {
        v13 = v11 + 1;
        v14 = 2 * v13;
        if ( !is_mul_ok(v13, 2u) )
          v14 = -1;
        v15 = (unsigned __int16 *)operator new(v14, (const struct std::nothrow_t *)std::nothrow);
        v4 = v15;
        v25 = v15;
        if ( v15 )
        {
          v16 = *(unsigned __int16 **)Buffer;
          v22 = 0;
          if ( !v13 || (ResourceString = 0, v13 > 0x7FFFFFFF) )
            ResourceString = -2147024809;
          v22 = ResourceString;
          if ( ResourceString < 0 )
          {
            if ( v13 )
              *v15 = 0;
          }
          else
          {
            v17 = 2147483646;
            v30 = 2147483646;
            v28 = *(unsigned __int16 **)Buffer;
            v29 = v13;
            v18 = v15;
            v26 = v15;
            ResourceString = 0;
            v19 = 0;
            v27 = 0;
            while ( v13 )
            {
              if ( !v17 )
                goto LABEL_32;
              v20 = *v16;
              if ( !*v16 )
                goto LABEL_32;
              v28 = ++v16;
              *v18++ = v20;
              v26 = v18;
              v29 = --v13;
              v30 = --v17;
              v27 = ++v19;
            }
            v26 = --v18;
            v27 = v19 - 1;
            ResourceString = -2147024774;
LABEL_32:
            *v18 = 0;
            v22 = ResourceString;
          }
          if ( ResourceString >= 0 )
          {
            *a2 = v4;
            v4 = 0;
            v25 = 0;
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
  operator delete((void *)lpSource);
  operator delete(v4);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140002014  mov     r11, rsp
0x140002017  mov     [r11+18h], rbx
0x14000201b  mov     [r11+20h], rsi
0x14000201f  push    rdi
0x140002020  push    r14
0x140002022  push    r15
0x140002024  sub     rsp, 0C0h
0x14000202b  mov     rax, cs:__security_cookie
0x140002032  xor     rax, rsp
0x140002035  mov     [rsp+0D8h+var_28], rax
0x14000203d  mov     r14, rdx
0x140002040  mov     rbx, rcx
0x140002043  xor     r15d, r15d
0x140002046  mov     [rsp+0D8h+lpSource], r15
0x14000204b  mov     esi, r15d
0x14000204e  mov     [r11-78h], r15
0x140002052  mov     [r11-80h], r15
0x140002056  xorps   xmm0, xmm0
0x140002059  movups  xmmword ptr [r11-48h], xmm0
0x14000205e  movups  xmmword ptr [r11-38h], xmm0
0x140002063  mov     [rsp+0D8h+var_94], r15d
0x140002068  mov     [rdx], r15
0x14000206b  add     rcx, 48h ; 'H'
0x14000206f  mov     al, [rcx]
0x140002071  test    al, al
0x140002073  jnz     short loc_1400020A3
0x140002075  mov     eax, 0C0A0001Bh
0x14000207a  mov     rcx, [rsp+0D8h+var_28]
0x140002082  xor     rcx, rsp; StackCookie
0x140002085  call    __security_check_cookie
0x14000208a  lea     r11, [rsp+0D8h+var_18]
0x140002092  mov     rbx, [r11+30h]
0x140002096  mov     rsi, [r11+38h]
0x14000209a  mov     rsp, r11
0x14000209d  pop     r15
0x14000209f  pop     r14
0x1400020a1  pop     rdi
0x1400020a2  retn
0x1400020a3  call    cs:__imp_?GetActionType@CDriveConfiguration@@QEAA?AW4BDECFG_ACTION_TYPE@@XZ; CDriveConfiguration::GetActionType(void)
0x1400020a9  sub     eax, 1
0x1400020ac  jz      short loc_1400020F1
0x1400020ae  sub     eax, 1
0x1400020b1  jz      short loc_1400020DA
0x1400020b3  sub     eax, 1
0x1400020b6  jz      short loc_1400020C3
0x1400020b8  mov     ebx, 0C0A0001Bh
0x1400020bd  mov     [rsp+0D8h+var_98], ebx
0x1400020c1  jmp     short loc_14000210C
0x1400020c3  lea     r9, [rsp+0D8h+var_48]; unsigned __int64 *
0x1400020cb  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x1400020d0  mov     rcx, rbx; this
0x1400020d3  call    ?GetActionTemplateUnallocatedSpace@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetActionTemplateUnallocatedSpace(ulong,ulong *,unsigned __int64 *)
0x1400020d8  jmp     short loc_140002106
0x1400020da  lea     r9, [rsp+0D8h+var_48]; unsigned __int64 *
0x1400020e2  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x1400020e7  mov     rcx, rbx; this
0x1400020ea  call    ?GetActionTemplateMerge@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetActionTemplateMerge(ulong,ulong *,unsigned __int64 *)
0x1400020ef  jmp     short loc_140002106
0x1400020f1  lea     r9, [rsp+0D8h+var_48]; unsigned __int64 *
0x1400020f9  lea     r8, [rsp+0D8h+var_94]; unsigned int *
0x1400020fe  mov     rcx, rbx; this
0x140002101  call    ?GetActionTemplateSplit@CBdeCfgConsole@@AEAAJKPEAKPEA_K@Z; CBdeCfgConsole::GetActionTemplateSplit(ulong,ulong *,unsigned __int64 *)
0x140002106  mov     ebx, eax
0x140002108  mov     [rsp+0D8h+var_98], eax
0x14000210c  test    ebx, ebx
0x14000210e  js      loc_1400022A7
0x140002114  lea     rdx, [rsp+0D8h+lpSource]
0x140002119  mov     ecx, [rsp+0D8h+var_94]
0x14000211d  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140002123  mov     ebx, eax
0x140002125  mov     [rsp+0D8h+var_98], eax
0x140002129  test    eax, eax
0x14000212b  js      loc_1400022A7
0x140002131  lea     rax, [rsp+0D8h+var_48]
0x140002139  mov     [rsp+0D8h+Arguments], rax; Arguments
0x14000213e  mov     [rsp+0D8h+nSize], r15d; nSize
0x140002143  lea     rax, [rsp+0D8h+Buffer]
0x140002148  mov     [rsp+0D8h+lpBuffer], rax; lpBuffer
0x14000214d  xor     r9d, r9d; dwLanguageId
0x140002150  xor     r8d, r8d; dwMessageId
0x140002153  mov     rdx, [rsp+0D8h+lpSource]; lpSource
0x140002158  mov     ecx, 2500h; dwFlags
0x14000215d  call    cs:__imp_FormatMessageW
0x140002163  test    eax, eax
0x140002165  jnz     short loc_140002185
0x140002167  call    cs:__imp_GetLastError
0x14000216d  mov     ebx, eax
0x14000216f  test    eax, eax
0x140002171  jle     short loc_14000217C
0x140002173  movzx   ebx, ax
0x140002176  or      ebx, 80070000h
0x14000217c  mov     [rsp+0D8h+var_98], ebx
0x140002180  jmp     loc_1400022A7
0x140002185  lea     edi, [rax+1]
0x140002188  mov     eax, 2
0x14000218d  mul     rdi
0x140002190  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140002197  cmovb   rax, rcx
0x14000219b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400021a2  mov     rcx, rax; unsigned __int64
0x1400021a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400021aa  mov     rsi, rax
0x1400021ad  mov     [rsp+0D8h+var_78], rax
0x1400021b2  test    rax, rax
0x1400021b5  jnz     short loc_1400021BE
0x1400021b7  mov     ebx, 8007000Eh
0x1400021bc  jmp     short loc_14000217C
0x1400021be  mov     rdx, qword ptr [rsp+0D8h+Buffer]
0x1400021c3  mov     [rsp+0D8h+var_90], r15d
0x1400021c8  test    rdi, rdi
0x1400021cb  jz      short loc_1400021D9
0x1400021cd  mov     ebx, r15d
0x1400021d0  cmp     rdi, 7FFFFFFFh
0x1400021d7  jbe     short loc_1400021DE
0x1400021d9  mov     ebx, 80070057h
0x1400021de  mov     [rsp+0D8h+var_90], ebx
0x1400021e2  test    ebx, ebx
0x1400021e4  js      loc_140002289
0x1400021ea  mov     r8d, 7FFFFFFEh
0x1400021f0  mov     [rsp+0D8h+var_50], r8
0x1400021f8  mov     [rsp+0D8h+var_60], rdx
0x1400021fd  mov     [rsp+0D8h+var_58], rdi
0x140002205  mov     rcx, rsi
0x140002208  mov     [rsp+0D8h+var_70], rcx
0x14000220d  mov     ebx, r15d
0x140002210  mov     rax, r15
0x140002213  mov     [rsp+0D8h+var_68], rax
0x140002218  test    rdi, rdi
0x14000221b  jz      short loc_140002267
0x14000221d  test    r8, r8
0x140002220  jz      short loc_140002262
0x140002222  movzx   r9d, word ptr [rdx]
0x140002226  test    r9w, r9w
0x14000222a  jz      short loc_140002262
0x14000222c  add     rdx, 2
0x140002230  mov     [rsp+0D8h+var_60], rdx
0x140002235  mov     [rcx], r9w
0x140002239  add     rcx, 2
0x14000223d  mov     [rsp+0D8h+var_70], rcx
0x140002242  dec     rdi
0x140002245  mov     [rsp+0D8h+var_58], rdi
0x14000224d  dec     r8
0x140002250  mov     [rsp+0D8h+var_50], r8
0x140002258  inc     rax
0x14000225b  mov     [rsp+0D8h+var_68], rax
0x140002260  jmp     short loc_140002218
0x140002262  test    rdi, rdi
0x140002265  jnz     short loc_14000227D
0x140002267  sub     rcx, 2
0x14000226b  mov     [rsp+0D8h+var_70], rcx
0x140002270  dec     rax
0x140002273  mov     [rsp+0D8h+var_68], rax
0x140002278  mov     ebx, 8007007Ah
0x14000227d  mov     eax, r15d
0x140002280  mov     [rcx], ax
0x140002283  mov     [rsp+0D8h+var_90], ebx
0x140002287  jmp     short loc_140002294
0x140002289  test    rdi, rdi
0x14000228c  jz      short loc_140002294
0x14000228e  mov     eax, r15d
0x140002291  mov     [rsi], ax
0x140002294  mov     [rsp+0D8h+var_98], ebx
0x140002298  test    ebx, ebx
0x14000229a  js      short loc_1400022A7
0x14000229c  mov     [r14], rsi
0x14000229f  mov     rsi, r15
0x1400022a2  mov     [rsp+0D8h+var_78], r15
0x1400022a7  mov     rcx, [rsp+0D8h+lpSource]; Block
0x1400022ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400022b1  mov     rcx, rsi; Block
0x1400022b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400022b9  mov     rcx, qword ptr [rsp+0D8h+Buffer]; hMem
0x1400022be  test    rcx, rcx
0x1400022c1  jz      short loc_1400022C9
0x1400022c3  call    cs:__imp_LocalFree
0x1400022c9  mov     eax, ebx
0x1400022cb  jmp     loc_14000207A
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
