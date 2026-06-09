# ConversionFunctions::ConvertXPathNumberToXPathString(double,String &)

- ea: `0x18000a8f4`
- end: `0x18000aadf`
- name: `?ConvertXPathNumberToXPathString@ConversionFunctions@@CAJNAEAVString@@@Z`
- size: `491`
- prototype: `static int(double, struct String *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ab90`

## callees

- `0x18000a640`
- `0x18000a690`
- `0x18000a6dc`
- `0x18000a8f4`
- `0x180010f08`
- `0x180011840`

## import_xrefs

- `msvcrt!_ecvt_s` at `0x18000a979`
- `msvcrt!_ecvt_s` at `0x18000a979`

## pseudocode

```c
__int64 __fastcall ConversionFunctions::ConvertXPathNumberToXPathString(double a1, struct String *a2)
{
  __int64 v3; // r9
  int v4; // ebx
  __int64 v5; // r9
  signed int v6; // esi
  signed int i; // edi
  unsigned int v8; // edi
  unsigned int v9; // esi
  unsigned int v10; // ecx
  char v11; // dl
  char v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // esi
  unsigned int PtDec; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  int PtSign; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v19; // [rsp+38h] [rbp-C8h] BYREF
  char v20; // [rsp+3Ah] [rbp-C6h]
  int v21; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 *Src; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v23; // [rsp+48h] [rbp-B8h]
  char Buffer[352]; // [rsp+50h] [rbp-B0h] BYREF

  v20 = 0;
  Src = (unsigned __int16 *)&v19;
  v21 = 2;
  v19 = 0;
  v17 = 0;
  PtSign = 0;
  LODWORD(v23) = 0;
  if ( _ecvt_s(Buffer, 0x15Du, a1, 347, (int *)&v17, &PtSign) )
  {
    v4 = -2147467259;
    goto LABEL_23;
  }
  if ( !PtSign || (v4 = STRU::Append((STRU *)&v19, L"-", 0), v4 >= 0) )
  {
    if ( (int)v17 > 0 )
    {
      v4 = STRU::AppendA((STRU *)&v19, Buffer, v17, v3, PtDec);
      if ( v4 < 0 )
        goto LABEL_23;
      v8 = v17;
      v11 = 0;
      v9 = v17;
      v10 = v17;
      if ( v17 >= 0x15D )
        goto LABEL_18;
    }
    else
    {
      v4 = STRU::Append((STRU *)&v19, L"0.", 0);
      if ( v4 < 0 )
        goto LABEL_23;
      v6 = -v17;
      for ( i = 0; i < v6; ++i )
      {
        v4 = STRU::Append((STRU *)&v19, L"0", 0);
        if ( v4 < 0 )
          goto LABEL_23;
      }
      v8 = 0;
      v9 = 0;
      v10 = 0;
      v11 = 1;
    }
    do
    {
      v12 = Buffer[v10];
      if ( !v12 )
        break;
      v13 = ++v10;
      if ( v12 == 48 )
        v13 = v9;
      v9 = v13;
    }
    while ( v10 < 0x15D );
LABEL_18:
    v14 = v9 - v8;
    if ( !v14
      || (v11 || (v4 = STRU::Append((STRU *)&v19, L".", 0), v4 >= 0))
      && (v4 = STRU::AppendA((STRU *)&v19, &Buffer[v8], v14, v5, PtDec), v4 >= 0) )
    {
      v4 = String::Initialize(a2, Src, (unsigned int)v23);
    }
  }
LABEL_23:
  BUFFER::~BUFFER((BUFFER *)&v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a8f4  mov     [rsp-8+arg_10], rbx
0x18000a8f9  mov     [rsp-8+arg_18], rsi
0x18000a8fe  push    rbp
0x18000a8ff  push    rdi
0x18000a900  push    r14
0x18000a902  lea     rbp, [rsp-0C0h]
0x18000a90a  sub     rsp, 1C0h
0x18000a911  mov     rax, cs:__security_cookie
0x18000a918  xor     rax, rsp
0x18000a91b  mov     [rbp+0D0h+var_20], rax
0x18000a922  lea     rax, [rsp+1D0h+var_198]
0x18000a927  mov     [rsp+1D0h+var_196], 0
0x18000a92c  mov     [rsp+1D0h+Src], rax
0x18000a931  lea     rcx, [rsp+1D0h+Buffer]; Buffer
0x18000a936  xor     eax, eax
0x18000a938  mov     [rsp+1D0h+var_194], 2
0x18000a940  mov     [rsp+1D0h+var_198], ax
0x18000a945  mov     r9d, 15Bh; DigitCount
0x18000a94b  mov     [rsp+1D0h+var_1A0], eax
0x18000a94f  mov     r14, rdx
0x18000a952  mov     [rsp+1D0h+var_19C], eax
0x18000a956  movaps  xmm2, xmm0; Value
0x18000a959  lea     rax, [rsp+1D0h+var_19C]
0x18000a95e  mov     dword ptr [rsp+1D0h+var_188], 0
0x18000a966  mov     [rsp+1D0h+PtSign], rax; PtSign
0x18000a96b  lea     edx, [r9+2]; BufferCount
0x18000a96f  lea     rax, [rsp+1D0h+var_1A0]
0x18000a974  mov     [rsp+1D0h+PtDec], rax; unsigned int
0x18000a979  call    cs:__imp__ecvt_s
0x18000a97f  test    eax, eax
0x18000a981  jz      short loc_18000A98D
0x18000a983  mov     ebx, 80004005h
0x18000a988  jmp     loc_18000AAAC
0x18000a98d  cmp     [rsp+1D0h+var_19C], 0
0x18000a992  jz      short loc_18000A9B2
0x18000a994  xor     r8d, r8d; unsigned int
0x18000a997  lea     rdx, asc_1800171E4; "-"
0x18000a99e  lea     rcx, [rsp+1D0h+var_198]; this
0x18000a9a3  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000a9a8  mov     ebx, eax
0x18000a9aa  test    eax, eax
0x18000a9ac  js      loc_18000AAAC
0x18000a9b2  mov     r8d, [rsp+1D0h+var_1A0]; unsigned int
0x18000a9b7  lea     rcx, [rsp+1D0h+var_198]; this
0x18000a9bc  test    r8d, r8d
0x18000a9bf  jg      short loc_18000AA12
0x18000a9c1  xor     r8d, r8d; unsigned int
0x18000a9c4  lea     rdx, a0_0; "0."
0x18000a9cb  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000a9d0  mov     ebx, eax
0x18000a9d2  test    eax, eax
0x18000a9d4  js      loc_18000AAAC
0x18000a9da  mov     esi, [rsp+1D0h+var_1A0]
0x18000a9de  neg     esi
0x18000a9e0  xor     edi, edi
0x18000a9e2  cmp     edi, esi
0x18000a9e4  jge     short loc_18000AA08
0x18000a9e6  xor     r8d, r8d; unsigned int
0x18000a9e9  lea     rdx, a0; "0"
0x18000a9f0  lea     rcx, [rsp+1D0h+var_198]; this
0x18000a9f5  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000a9fa  mov     ebx, eax
0x18000a9fc  test    eax, eax
0x18000a9fe  js      loc_18000AAAC
0x18000aa04  inc     edi
0x18000aa06  jmp     short loc_18000A9E2
0x18000aa08  xor     edi, edi
0x18000aa0a  xor     esi, esi
0x18000aa0c  xor     ecx, ecx
0x18000aa0e  mov     dl, 1
0x18000aa10  jmp     short loc_18000AA38
0x18000aa12  lea     rdx, [rsp+1D0h+Buffer]; char *
0x18000aa17  call    ?AppendA@STRU@@QEAAJPEBDKIK@Z; STRU::AppendA(char const *,ulong,uint,ulong)
0x18000aa1c  mov     ebx, eax
0x18000aa1e  test    eax, eax
0x18000aa20  js      loc_18000AAAC
0x18000aa26  mov     edi, [rsp+1D0h+var_1A0]
0x18000aa2a  xor     dl, dl
0x18000aa2c  mov     esi, edi
0x18000aa2e  mov     ecx, edi
0x18000aa30  cmp     edi, 15Dh
0x18000aa36  jnb     short loc_18000AA59
0x18000aa38  mov     eax, ecx
0x18000aa3a  mov     r8b, [rsp+rax+1D0h+Buffer]
0x18000aa3f  test    r8b, r8b
0x18000aa42  jz      short loc_18000AA59
0x18000aa44  inc     ecx
0x18000aa46  cmp     r8b, 30h ; '0'
0x18000aa4a  mov     eax, ecx
0x18000aa4c  cmovz   eax, esi
0x18000aa4f  mov     esi, eax
0x18000aa51  cmp     ecx, 15Dh
0x18000aa57  jb      short loc_18000AA38
0x18000aa59  sub     esi, edi
0x18000aa5b  jz      short loc_18000AA98
0x18000aa5d  test    dl, dl
0x18000aa5f  jnz     short loc_18000AA7B
0x18000aa61  xor     r8d, r8d; unsigned int
0x18000aa64  lea     rdx, asc_1800171F0; "."
0x18000aa6b  lea     rcx, [rsp+1D0h+var_198]; this
0x18000aa70  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000aa75  mov     ebx, eax
0x18000aa77  test    eax, eax
0x18000aa79  js      short loc_18000AAAC
0x18000aa7b  mov     eax, edi
0x18000aa7d  lea     rdx, [rsp+1D0h+Buffer]
0x18000aa82  add     rdx, rax; char *
0x18000aa85  lea     rcx, [rsp+1D0h+var_198]; this
0x18000aa8a  mov     r8d, esi; unsigned int
0x18000aa8d  call    ?AppendA@STRU@@QEAAJPEBDKIK@Z; STRU::AppendA(char const *,ulong,uint,ulong)
0x18000aa92  mov     ebx, eax
0x18000aa94  test    eax, eax
0x18000aa96  js      short loc_18000AAAC
0x18000aa98  mov     r8d, dword ptr [rsp+1D0h+var_188]; unsigned __int64
0x18000aa9d  mov     rcx, r14; this
0x18000aaa0  mov     rdx, [rsp+1D0h+Src]; Src
0x18000aaa5  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000aaaa  mov     ebx, eax
0x18000aaac  lea     rcx, [rsp+1D0h+var_198]; this
0x18000aab1  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000aab6  mov     eax, ebx
0x18000aab8  mov     rcx, [rbp+0D0h+var_20]
0x18000aabf  xor     rcx, rsp; StackCookie
0x18000aac2  call    __security_check_cookie
0x18000aac7  lea     r11, [rsp+1D0h+var_10]
0x18000aacf  mov     rbx, [r11+30h]
0x18000aad3  mov     rsi, [r11+38h]
0x18000aad7  mov     rsp, r11
0x18000aada  pop     r14
0x18000aadc  pop     rdi
0x18000aadd  pop     rbp
0x18000aade  retn
```
