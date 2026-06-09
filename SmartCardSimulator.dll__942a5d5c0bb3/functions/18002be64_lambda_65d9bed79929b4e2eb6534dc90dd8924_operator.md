# _lambda_65d9bed79929b4e2eb6534dc90dd8924_::operator()

- ea: `0x18002be64`
- end: `0x18002bfc8`
- name: `_lambda_65d9bed79929b4e2eb6534dc90dd8924_::operator()`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002f220`
- `0x18002fd14`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x1800287d0`
- `0x18002be64`
- `0x18003bf34`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x18002bf80`: `FileSystem::DedicatedFile::CreateEf`

## pseudocode

```c
PVOID __fastcall lambda_65d9bed79929b4e2eb6534dc90dd8924_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID result; // rax
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // r15
  int *v9; // rax
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  char v13; // r11
  __int64 v14[2]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v15[16]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v16[64]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v17; // [rsp+C0h] [rbp-48h] BYREF

  memset_0(v16, 0, sizeof(v16));
  if ( **(_BYTE **)a1 )
    v2 = ReportIndentTracker::Enter();
  else
    v2 = ReportIndentTracker::Exit();
  v14[0] = (__int64)v16;
  v14[1] = (__int64)&v17;
  LOBYTE(v4) = **(_BYTE **)a1 != 0 ? 62 : 60;
  ReportIndentTracker::Format(v14, v2, v3, v4);
  result = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v6 = *(_QWORD *)(a1 + 32);
    v7 = *(_QWORD *)(v6 + 32);
    v8 = *(_QWORD *)(v6 + 16);
    v9 = *(int **)(a1 + 24);
    v10 = v9[2];
    v11 = v9[1];
    v12 = *v9;
    *(_OWORD *)v14 = *(_OWORD *)log_byterange<std::vector<unsigned char> const &>(v15, *(_QWORD *)(a1 + 8) + 40LL);
    return (PVOID)WPP_SF_ss_HEX_DLLLss(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (__int64)"FileSystem::DedicatedFile::CreateEf",
                    (__int64)v14,
                    v13,
                    v12,
                    v11,
                    v10,
                    v8,
                    v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002be64  push    rbx
0x18002be66  push    rsi
0x18002be67  push    rdi
0x18002be68  push    r12
0x18002be6a  push    r14
0x18002be6c  push    r15
0x18002be6e  sub     rsp, 0D8h
0x18002be75  mov     rax, cs:__security_cookie
0x18002be7c  xor     rax, rsp
0x18002be7f  mov     [rsp+108h+var_48], rax
0x18002be87  mov     r12, rcx
0x18002be8a  xor     edx, edx; Val
0x18002be8c  lea     r8d, [rdx+40h]; Size
0x18002be90  lea     rcx, [rsp+108h+var_88]; void *
0x18002be98  call    memset_0
0x18002be9d  mov     rax, [r12]
0x18002bea1  cmp     byte ptr [rax], 0
0x18002bea4  jz      short loc_18002BEAD
0x18002bea6  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x18002beab  jmp     short loc_18002BEB2
0x18002bead  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18002beb2  mov     edx, eax
0x18002beb4  lea     rax, [rsp+108h+var_88]
0x18002bebc  mov     [rsp+108h+var_A8], rax
0x18002bec1  lea     rax, [rsp+108h+var_48]
0x18002bec9  mov     [rsp+108h+var_A8+8], rax
0x18002bece  mov     rax, [r12]
0x18002bed2  mov     cl, [rax]
0x18002bed4  neg     cl
0x18002bed6  sbb     r9b, r9b
0x18002bed9  and     r9b, 2
0x18002bedd  add     r9b, 3Ch ; '<'
0x18002bee1  lea     rcx, [rsp+108h+var_A8]
0x18002bee6  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18002beeb  lea     rcx, WPP_GLOBAL_Control
0x18002bef2  mov     rax, cs:WPP_GLOBAL_Control
0x18002bef9  cmp     rax, rcx
0x18002befc  jz      loc_18002BFA5
0x18002bf02  test    byte ptr [rax+1Ch], 2
0x18002bf06  jz      loc_18002BFA5
0x18002bf0c  cmp     byte ptr [rax+19h], 5
0x18002bf10  jb      loc_18002BFA5
0x18002bf16  mov     rax, [r12+20h]
0x18002bf1b  mov     r14, [rax+20h]
0x18002bf1f  mov     r15, [rax+10h]
0x18002bf23  mov     rax, [r12+18h]
0x18002bf28  mov     ebx, [rax+8]
0x18002bf2b  mov     edi, [rax+4]
0x18002bf2e  mov     esi, [rax]
0x18002bf30  mov     rax, [r12+10h]
0x18002bf35  movzx   r11d, word ptr [rax+4]
0x18002bf3a  mov     rdx, [r12+8]
0x18002bf3f  add     rdx, 28h ; '('
0x18002bf43  lea     rcx, [rsp+108h+var_98]
0x18002bf48  call    ??$log_byterange@AEBV?$vector@EV?$allocator@E@std@@@std@@@@YA?AUxbyterange@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; log_byterange<std::vector<uchar> const &>(std::vector<uchar> const &)
0x18002bf4d  movups  xmm0, xmmword ptr [rax]
0x18002bf50  movdqu  xmmword ptr [rsp+108h+var_A8], xmm0
0x18002bf56  mov     edx, 61h ; 'a'
0x18002bf5b  mov     [rsp+108h+var_B0], r14; __int64
0x18002bf60  mov     [rsp+108h+var_B8], r15; __int64
0x18002bf65  mov     dword ptr [rsp+108h+var_C0], ebx; char
0x18002bf69  mov     dword ptr [rsp+108h+var_C8], edi; char
0x18002bf6d  mov     dword ptr [rsp+108h+var_D0], esi; char
0x18002bf71  mov     dword ptr [rsp+108h+var_D8], r11d; char
0x18002bf76  lea     rax, [rsp+108h+var_A8]
0x18002bf7b  mov     [rsp+108h+var_E0], rax; __int64
0x18002bf80  lea     rax, aFilesystemDedi_1; "FileSystem::DedicatedFile::CreateEf"
0x18002bf87  mov     [rsp+108h+var_E8], rax; __int64
0x18002bf8c  lea     r9, [rsp+108h+var_88]
0x18002bf94  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf9b  mov     rcx, [rcx+10h]; LoggerHandle
0x18002bf9f  call    WPP_SF_ss_HEX_DLLLss
0x18002bfa4  nop
0x18002bfa5  jmp     short $+2
0x18002bfa7  mov     rcx, [rsp+108h+var_48]
0x18002bfaf  xor     rcx, rsp; StackCookie
0x18002bfb2  call    __security_check_cookie
0x18002bfb7  add     rsp, 0D8h
0x18002bfbe  pop     r15
0x18002bfc0  pop     r14
0x18002bfc2  pop     r12
0x18002bfc4  pop     rdi
0x18002bfc5  pop     rsi
0x18002bfc6  pop     rbx
0x18002bfc7  retn
```
