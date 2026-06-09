# CUniscribe::ItemizeString(tagUSP_CLIENT *,ushort,int *,ushort *,int,int,ushort,int)

- ea: `0x180026d10`
- end: `0x180026e14`
- name: `?ItemizeString@CUniscribe@@QEAAHPEAUtagUSP_CLIENT@@GPEAHPEAGHHGH@Z`
- size: `260`
- prototype: `__int64 __fastcall(CUniscribe *__hidden this, struct tagUSP_CLIENT *, unsigned __int16, int *, WCHAR *pwcInChars, int cInChars, int, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180026e40`
- `0x18008b030`

## callees

- `0x180026d10`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180026d65`
- `KERNEL32!GetThreadLocale` at `0x180026d65`
- `USP10!ScriptItemize` at `0x180026de6`
- `USP10!ScriptItemize` at `0x180026de6`

## pseudocode

```c
__int64 __fastcall CUniscribe::ItemizeString(
        CUniscribe *this,
        struct tagUSP_CLIENT *a2,
        __int16 a3,
        int *a4,
        WCHAR *pwcInChars,
        int cInChars,
        int a7,
        unsigned __int16 a8,
        int a9)
{
  __int64 v9; // rax
  __int16 v10; // dx
  SCRIPT_ITEM *pItems; // r15
  unsigned __int16 v14; // ax
  SCRIPT_CONTROL *p_psControl; // rbx
  const SCRIPT_STATE *psState; // rdi
  __int16 ThreadLocale; // ax
  __int64 result; // rax
  int pcItems[4]; // [rsp+40h] [rbp-10h] BYREF
  CUniscribe *v20; // [rsp+80h] [rbp+30h] BYREF
  SCRIPT_CONTROL psControl; // [rsp+88h] [rbp+38h] BYREF

  v20 = this;
  v9 = *(_QWORD *)a2;
  v10 = 0;
  pItems = *(SCRIPT_ITEM **)(v9 + 16);
  psControl = 0;
  LOWORD(v20) = 0;
  pcItems[0] = 0;
  if ( a7 )
  {
    v14 = a8;
    p_psControl = &psControl;
    psState = (const SCRIPT_STATE *)&v20;
    if ( !a8 )
    {
      ThreadLocale = GetThreadLocale();
      v10 = (__int16)v20;
      v14 = ThreadLocale & 0x3FF;
    }
    *(_WORD *)&psControl = v14;
    psControl = (SCRIPT_CONTROL)((*(_DWORD *)&psControl ^ (a9 << 23)) & 0x800000 ^ *(_DWORD *)&psControl);
    if ( psControl == 1 )
      v10 ^= (v10 ^ (a3 << 11)) & 0x800;
    LOWORD(v20) = v10 ^ ((unsigned __int8)a3 ^ (unsigned __int8)v10) & 0x1F;
  }
  else
  {
    p_psControl = 0;
    psState = 0;
  }
  if ( ScriptItemize(pwcInChars, cInChars, cInChars + 1, p_psControl, psState, pItems, pcItems) < 0 )
    return 0;
  result = (unsigned int)pcItems[0];
  *a4 = pcItems[0];
  return result;
}

```

## disassembly

```asm
0x180026d10  mov     [rsp-28h+arg_10], rbx
0x180026d15  mov     [rsp-28h+arg_18], rsi
0x180026d1a  mov     [rsp-28h+arg_0], rcx
0x180026d1f  push    rbp
0x180026d20  push    rdi
0x180026d21  push    r12
0x180026d23  push    r14
0x180026d25  push    r15
0x180026d27  mov     rbp, rsp
0x180026d2a  sub     rsp, 50h
0x180026d2e  mov     rax, [rdx]
0x180026d31  xor     r12d, r12d
0x180026d34  mov     edx, r12d
0x180026d37  mov     r14, r9
0x180026d3a  movzx   esi, r8w
0x180026d3e  mov     r15, [rax+10h]
0x180026d42  mov     dword ptr [rbp+psControl.uDefaultLanguage], r12d
0x180026d46  mov     word ptr [rbp+arg_0], dx
0x180026d4a  mov     [rbp+var_10], r12d
0x180026d4e  cmp     [rbp+arg_30], r12d
0x180026d52  jz      short loc_180026DBF
0x180026d54  movzx   eax, [rbp+arg_38]
0x180026d58  lea     rbx, [rbp+psControl]
0x180026d5c  lea     rdi, [rbp+arg_0]
0x180026d60  test    ax, ax
0x180026d63  jnz     short loc_180026D77
0x180026d65  call    cs:__imp_GetThreadLocale
0x180026d6b  movzx   edx, word ptr [rbp+arg_0]
0x180026d6f  mov     ecx, 3FFh
0x180026d74  and     ax, cx
0x180026d77  mov     ecx, [rbp+arg_40]
0x180026d7a  shl     ecx, 17h
0x180026d7d  mov     word ptr [rbp+psControl.uDefaultLanguage], ax
0x180026d81  mov     eax, dword ptr [rbp+psControl.uDefaultLanguage]
0x180026d84  xor     ecx, eax
0x180026d86  and     ecx, 800000h
0x180026d8c  xor     eax, ecx
0x180026d8e  mov     dword ptr [rbp+psControl.uDefaultLanguage], eax
0x180026d91  cmp     ax, 1
0x180026d95  jnz     short loc_180026DAC
0x180026d97  movzx   eax, si
0x180026d9a  mov     ecx, 800h
0x180026d9f  shl     ax, 0Bh
0x180026da3  xor     ax, dx
0x180026da6  and     ax, cx
0x180026da9  xor     dx, ax
0x180026dac  movzx   eax, dx
0x180026daf  xor     ax, si
0x180026db2  and     ax, 1Fh
0x180026db6  xor     ax, dx
0x180026db9  mov     word ptr [rbp+arg_0], ax
0x180026dbd  jmp     short loc_180026DC5
0x180026dbf  mov     rbx, r12
0x180026dc2  mov     rdi, r12
0x180026dc5  mov     edx, [rbp+cInChars]; cInChars
0x180026dc8  lea     rax, [rbp+var_10]
0x180026dcc  mov     rcx, [rbp+pwcInChars]; pwcInChars
0x180026dd0  mov     r9, rbx; psControl
0x180026dd3  mov     [rsp+50h+pcItems], rax; pcItems
0x180026dd8  mov     [rsp+50h+pItems], r15; pItems
0x180026ddd  lea     r8d, [rdx+1]; cMaxItems
0x180026de1  mov     [rsp+50h+psState], rdi; psState
0x180026de6  call    cs:__imp_ScriptItemize
0x180026dec  test    eax, eax
0x180026dee  js      short loc_180026DF8
0x180026df0  mov     eax, [rbp+var_10]
0x180026df3  mov     [r14], eax
0x180026df6  jmp     short loc_180026DFB
0x180026df8  mov     eax, r12d
0x180026dfb  lea     r11, [rsp+50h+var_s0]
0x180026e00  mov     rbx, [r11+40h]
0x180026e04  mov     rsi, [r11+48h]
0x180026e08  mov     rsp, r11
0x180026e0b  pop     r15
0x180026e0d  pop     r14
0x180026e0f  pop     r12
0x180026e11  pop     rdi
0x180026e12  pop     rbp
0x180026e13  retn
```
