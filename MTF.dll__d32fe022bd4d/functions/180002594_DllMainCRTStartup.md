# __DllMainCRTStartup

- ea: `0x180002594`
- end: `0x1800027a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002550`

## callees

- `0x180002320`
- `0x180002594`
- `0x18000297e`
- `0x1800076a0`
- `0x18002bd10`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_18003F25C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003F260 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18003F260 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180002594  mov     [rsp+lpvReserved], r8
0x180002599  mov     [rsp+arg_8], edx
0x18000259d  mov     [rsp+arg_0], rcx
0x1800025a2  push    rbx
0x1800025a3  push    rsi
0x1800025a4  push    rdi
0x1800025a5  sub     rsp, 0F0h
0x1800025ac  mov     edi, edx
0x1800025ae  mov     rsi, rcx
0x1800025b1  mov     ebx, 1
0x1800025b6  cmp     edx, ebx
0x1800025b8  ja      short loc_1800025C0
0x1800025ba  mov     cs:__native_dllmain_reason, edx
0x1800025c0  test    edx, edx
0x1800025c2  jnz     short loc_1800025D7
0x1800025c4  cmp     cs:dword_18003F25C, edx
0x1800025ca  jnz     short loc_1800025D7
0x1800025cc  xor     ebx, ebx
0x1800025ce  mov     [rsp+108h+var_E8], ebx
0x1800025d2  jmp     loc_180002784
0x1800025d7  lea     eax, [rdx-1]
0x1800025da  cmp     eax, 1
0x1800025dd  ja      loc_180002664
0x1800025e3  mov     rax, cs:_pRawDllMain
0x1800025ea  test    rax, rax
0x1800025ed  jz      short loc_180002625
0x1800025ef  cmp     edx, 1
0x1800025f2  jnz     short loc_1800025FA
0x1800025f4  mov     cs:dword_18003F260, edx
0x1800025fa  mov     r8, [rsp+108h+lpvReserved]
0x180002602  call    cs:__guard_dispatch_icall_fptr
0x180002608  mov     ebx, eax
0x18000260a  mov     [rsp+108h+var_E8], eax
0x18000260e  jmp     short loc_180002625
0x180002610  xor     ebx, ebx
0x180002612  mov     [rsp+108h+var_E8], ebx
0x180002616  mov     edi, [rsp+108h+arg_8]
0x18000261d  mov     rsi, [rsp+108h+arg_0]
0x180002625  test    ebx, ebx
0x180002627  jz      loc_180002784
0x18000262d  mov     r8, [rsp+108h+lpvReserved]
0x180002635  mov     edx, edi
0x180002637  mov     rcx, rsi
0x18000263a  call    _CRT_INIT
0x18000263f  mov     ebx, eax
0x180002641  mov     [rsp+108h+var_E8], eax
0x180002645  jmp     short loc_18000265C
0x180002647  xor     ebx, ebx
0x180002649  mov     [rsp+108h+var_E8], ebx
0x18000264d  mov     edi, [rsp+108h+arg_8]
0x180002654  mov     rsi, [rsp+108h+arg_0]
0x18000265c  test    ebx, ebx
0x18000265e  jz      loc_180002784
0x180002664  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000266c  mov     edx, edi; fdwReason
0x18000266e  mov     rcx, rsi; hinstDLL
0x180002671  call    DllMain
0x180002676  mov     ebx, eax
0x180002678  mov     [rsp+108h+var_E8], eax
0x18000267c  jmp     short loc_180002693
0x18000267e  xor     ebx, ebx
0x180002680  mov     [rsp+108h+var_E8], ebx
0x180002684  mov     edi, [rsp+108h+arg_8]
0x18000268b  mov     rsi, [rsp+108h+arg_0]
0x180002693  cmp     edi, 1
0x180002696  jnz     short loc_18000270F
0x180002698  test    ebx, ebx
0x18000269a  jnz     short loc_18000270F
0x18000269c  xor     r8d, r8d; lpvReserved
0x18000269f  xor     edx, edx; fdwReason
0x1800026a1  mov     rcx, rsi; hinstDLL
0x1800026a4  call    DllMain
0x1800026a9  jmp     short loc_1800026BE
0x1800026ab  mov     edi, [rsp+108h+arg_8]
0x1800026b2  mov     rsi, [rsp+108h+arg_0]
0x1800026ba  mov     ebx, [rsp+108h+var_E8]
0x1800026be  xor     r8d, r8d
0x1800026c1  xor     edx, edx
0x1800026c3  mov     rcx, rsi
0x1800026c6  call    _CRT_INIT
0x1800026cb  jmp     short loc_1800026E0
0x1800026cd  mov     edi, [rsp+108h+arg_8]
0x1800026d4  mov     rsi, [rsp+108h+arg_0]
0x1800026dc  mov     ebx, [rsp+108h+var_E8]
0x1800026e0  mov     rax, cs:_pRawDllMain
0x1800026e7  test    rax, rax
0x1800026ea  jz      short loc_18000270F
0x1800026ec  xor     r8d, r8d
0x1800026ef  xor     edx, edx
0x1800026f1  mov     rcx, rsi
0x1800026f4  call    cs:__guard_dispatch_icall_fptr
0x1800026fa  jmp     short loc_18000270F
0x1800026fc  mov     edi, [rsp+108h+arg_8]
0x180002703  mov     rsi, [rsp+108h+arg_0]
0x18000270b  mov     ebx, [rsp+108h+var_E8]
0x18000270f  test    edi, edi
0x180002711  jz      short loc_180002718
0x180002713  cmp     edi, 3
0x180002716  jnz     short loc_180002784
0x180002718  mov     r8, [rsp+108h+lpvReserved]
0x180002720  mov     edx, edi
0x180002722  mov     rcx, rsi
0x180002725  call    _CRT_INIT
0x18000272a  mov     ebx, eax
0x18000272c  mov     [rsp+108h+var_E8], eax
0x180002730  jmp     short loc_180002747
0x180002732  xor     ebx, ebx
0x180002734  mov     [rsp+108h+var_E8], ebx
0x180002738  mov     edi, [rsp+108h+arg_8]
0x18000273f  mov     rsi, [rsp+108h+arg_0]
0x180002747  mov     rax, cs:_pRawDllMain
0x18000274e  test    rax, rax
0x180002751  jz      short loc_180002784
0x180002753  cmp     cs:dword_18003F260, 0
0x18000275a  jz      short loc_180002784
0x18000275c  mov     r8, [rsp+108h+lpvReserved]
0x180002764  mov     edx, edi
0x180002766  mov     rcx, rsi
0x180002769  call    cs:__guard_dispatch_icall_fptr
0x18000276f  mov     ebx, eax
0x180002771  mov     [rsp+108h+var_E8], eax
0x180002775  jmp     short loc_180002784
0x180002777  xor     ebx, ebx
0x180002779  mov     [rsp+108h+var_E8], ebx
0x18000277d  mov     edi, [rsp+108h+arg_8]
0x180002784  cmp     edi, 1
0x180002787  ja      short loc_180002793
0x180002789  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002793  mov     eax, ebx
0x180002795  add     rsp, 0F0h
0x18000279c  pop     rdi
0x18000279d  pop     rsi
0x18000279e  pop     rbx
0x18000279f  retn
0x18002bdb3  push    rbp
0x18002bdb5  sub     rsp, 20h
0x18002bdb9  mov     rbp, rdx
0x18002bdbc  mov     rax, [rcx]
0x18002bdbf  mov     edx, [rax]
0x18002bdc1  mov     [rbp+0A8h], rcx
0x18002bdc8  mov     [rbp+28h], edx
0x18002bdcb  mov     eax, [rbp+28h]
0x18002bdce  cmp     eax, 0E06D7363h
0x18002bdd3  jnz     short loc_18002BDE9
0x18002bdd5  mov     rdx, [rbp+0A8h]
0x18002bddc  mov     ecx, [rbp+28h]
0x18002bddf  call    _XcptFilter_0
0x18002bde4  mov     [rbp+30h], eax
0x18002bde7  jmp     short loc_18002BDF0
0x18002bde9  mov     dword ptr [rbp+30h], 0
0x18002bdf0  mov     eax, [rbp+30h]
0x18002bdf3  add     rsp, 20h
0x18002bdf7  pop     rbp
0x18002bdf8  retn
0x18002bdfa  push    rbp
0x18002bdfc  sub     rsp, 20h
0x18002be00  mov     rbp, rdx
0x18002be03  mov     rax, [rcx]
0x18002be06  mov     edx, [rax]
0x18002be08  mov     [rbp+0B0h], rcx
0x18002be0f  mov     [rbp+38h], edx
0x18002be12  mov     eax, [rbp+38h]
0x18002be15  cmp     eax, 0E06D7363h
0x18002be1a  jnz     short loc_18002BE30
0x18002be1c  mov     rdx, [rbp+0B0h]
0x18002be23  mov     ecx, [rbp+38h]
0x18002be26  call    _XcptFilter_0
0x18002be2b  mov     [rbp+40h], eax
0x18002be2e  jmp     short loc_18002BE37
0x18002be30  mov     dword ptr [rbp+40h], 0
0x18002be37  mov     eax, [rbp+40h]
0x18002be3a  add     rsp, 20h
0x18002be3e  pop     rbp
0x18002be3f  retn
0x18002be41  push    rbp
0x18002be43  sub     rsp, 20h
0x18002be47  mov     rbp, rdx
0x18002be4a  mov     rax, [rcx]
0x18002be4d  mov     edx, [rax]
0x18002be4f  mov     [rbp+0B8h], rcx
0x18002be56  mov     [rbp+48h], edx
0x18002be59  mov     eax, [rbp+48h]
0x18002be5c  cmp     eax, 0E06D7363h
0x18002be61  jnz     short loc_18002BE77
0x18002be63  mov     rdx, [rbp+0B8h]
0x18002be6a  mov     ecx, [rbp+48h]
0x18002be6d  call    _XcptFilter_0
0x18002be72  mov     [rbp+50h], eax
0x18002be75  jmp     short loc_18002BE7E
0x18002be77  mov     dword ptr [rbp+50h], 0
0x18002be7e  mov     eax, [rbp+50h]
0x18002be81  add     rsp, 20h
0x18002be85  pop     rbp
0x18002be86  retn
0x18002be88  push    rbp
0x18002be8a  sub     rsp, 20h
0x18002be8e  mov     rbp, rdx
0x18002be91  mov     rax, [rcx]
0x18002be94  mov     edx, [rax]
0x18002be96  mov     [rbp+0C0h], rcx
0x18002be9d  mov     [rbp+58h], edx
0x18002bea0  mov     eax, [rbp+58h]
0x18002bea3  cmp     eax, 0E06D7363h
0x18002bea8  jnz     short loc_18002BEBE
0x18002beaa  mov     rdx, [rbp+0C0h]
0x18002beb1  mov     ecx, [rbp+58h]
0x18002beb4  call    _XcptFilter_0
0x18002beb9  mov     [rbp+60h], eax
0x18002bebc  jmp     short loc_18002BEC5
0x18002bebe  mov     dword ptr [rbp+60h], 0
0x18002bec5  mov     eax, [rbp+60h]
0x18002bec8  add     rsp, 20h
0x18002becc  pop     rbp
0x18002becd  retn
0x18002becf  push    rbp
0x18002bed1  sub     rsp, 20h
0x18002bed5  mov     rbp, rdx
0x18002bed8  mov     rax, [rcx]
0x18002bedb  mov     edx, [rax]
0x18002bedd  mov     [rbp+0C8h], rcx
0x18002bee4  mov     [rbp+68h], edx
0x18002bee7  mov     eax, [rbp+68h]
0x18002beea  cmp     eax, 0E06D7363h
0x18002beef  jnz     short loc_18002BF05
0x18002bef1  mov     rdx, [rbp+0C8h]
0x18002bef8  mov     ecx, [rbp+68h]
0x18002befb  call    _XcptFilter_0
0x18002bf00  mov     [rbp+70h], eax
0x18002bf03  jmp     short loc_18002BF0C
0x18002bf05  mov     dword ptr [rbp+70h], 0
0x18002bf0c  mov     eax, [rbp+70h]
0x18002bf0f  add     rsp, 20h
0x18002bf13  pop     rbp
0x18002bf14  retn
0x18002bf16  push    rbp
0x18002bf18  sub     rsp, 20h
0x18002bf1c  mov     rbp, rdx
0x18002bf1f  mov     rax, [rcx]
0x18002bf22  mov     edx, [rax]
0x18002bf24  mov     [rbp+0D0h], rcx
0x18002bf2b  mov     [rbp+78h], edx
0x18002bf2e  mov     eax, [rbp+78h]
0x18002bf31  cmp     eax, 0E06D7363h
0x18002bf36  jnz     short loc_18002BF4F
0x18002bf38  mov     rdx, [rbp+0D0h]
0x18002bf3f  mov     ecx, [rbp+78h]
0x18002bf42  call    _XcptFilter_0
0x18002bf47  mov     [rbp+80h], eax
0x18002bf4d  jmp     short loc_18002BF59
0x18002bf4f  mov     dword ptr [rbp+80h], 0
0x18002bf59  mov     eax, [rbp+80h]
0x18002bf5f  add     rsp, 20h
0x18002bf63  pop     rbp
0x18002bf64  retn
0x18002bf66  push    rbp
0x18002bf68  sub     rsp, 20h
0x18002bf6c  mov     rbp, rdx
0x18002bf6f  mov     rax, [rcx]
0x18002bf72  mov     edx, [rax]
0x18002bf74  mov     [rbp+0D8h], rcx
0x18002bf7b  mov     [rbp+88h], edx
0x18002bf81  mov     eax, [rbp+88h]
0x18002bf87  cmp     eax, 0E06D7363h
0x18002bf8c  jnz     short loc_18002BFA8
0x18002bf8e  mov     rdx, [rbp+0D8h]
0x18002bf95  mov     ecx, [rbp+88h]
0x18002bf9b  call    _XcptFilter_0
0x18002bfa0  mov     [rbp+90h], eax
0x18002bfa6  jmp     short loc_18002BFB2
0x18002bfa8  mov     dword ptr [rbp+90h], 0
0x18002bfb2  mov     eax, [rbp+90h]
0x18002bfb8  add     rsp, 20h
0x18002bfbc  pop     rbp
0x18002bfbd  retn
0x18002bfbf  push    rbp
0x18002bfc1  sub     rsp, 20h
0x18002bfc5  mov     rbp, rdx
0x18002bfc8  mov     rax, [rcx]
0x18002bfcb  mov     edx, [rax]
0x18002bfcd  mov     [rbp+0E0h], rcx
0x18002bfd4  mov     [rbp+98h], edx
0x18002bfda  mov     eax, [rbp+98h]
0x18002bfe0  cmp     eax, 0E06D7363h
0x18002bfe5  jnz     short loc_18002C001
0x18002bfe7  mov     rdx, [rbp+0E0h]
0x18002bfee  mov     ecx, [rbp+98h]
0x18002bff4  call    _XcptFilter_0
0x18002bff9  mov     [rbp+0A0h], eax
0x18002bfff  jmp     short loc_18002C00B
0x18002c001  mov     dword ptr [rbp+0A0h], 0
0x18002c00b  mov     eax, [rbp+0A0h]
0x18002c011  add     rsp, 20h
0x18002c015  pop     rbp
0x18002c016  retn
0x18002c018  push    rbp
0x18002c01a  sub     rsp, 20h
0x18002c01e  mov     rbp, rdx
0x18002c021  cmp     dword ptr [rbp+118h], 1
0x18002c028  ja      short loc_18002C034
0x18002c02a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
