# ZtUpdateClientCertConfigGlobal

- ea: `0x180012284`
- end: `0x180012407`
- name: `ZtUpdateClientCertConfigGlobal`
- size: `387`
- prototype: `__int64 __fastcall(int, __int64, const CERT_CONTEXT *, LPVOID **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180012410`

## callees

- `0x1800014b0`
- `0x18000dbcc`
- `0x180011f68`
- `0x180012284`
- `0x180015008`
- `0x18001690c`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18001239f`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800123aa`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18001239f`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800123aa`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180012346`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180012346`
- `CRYPT32!CertFreeCertificateContext` at `0x1800123c1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800123c1`

## pseudocode

```c
__int64 __fastcall ZtUpdateClientCertConfigGlobal(int a1, __int64 a2, const CERT_CONTEXT *a3, LPVOID **a4)
{
  LPVOID *v4; // rsi
  __int64 v5; // rbp
  const CERT_CONTEXT *v6; // r15
  unsigned int v10; // ebx
  int v11; // eax
  LPVOID v12; // rdx
  LPVOID lpMem; // [rsp+40h] [rbp-48h] BYREF

  v4 = 0;
  v5 = a1;
  v6 = 0;
  lpMem = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dqqqq(a1, a2, (_DWORD)a3, a1, a2, (__int64)a3, (__int64)a4);
  if ( a4 )
    *a4 = 0;
  if ( a2 && (unsigned int)v5 <= 1 )
  {
    v11 = ZtCopyClientCertConfig(a2, &lpMem);
    v10 = v11;
    if ( v11 )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
        WPP_SF_d(1035, 0xEu, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v11);
    }
    else
    {
      v12 = lpMem;
      v4 = (LPVOID *)g_rgpZtClientCerts[v5];
      lpMem = 0;
      v6 = (const CERT_CONTEXT *)g_rgpZtClientCertContext[v5];
      g_rgpZtClientCerts[v5] = (__int64)v12;
      g_rgpZtClientCertContext[v5] = 0;
      if ( a3 )
        g_rgpZtClientCertContext[v5] = (__int64)CertDuplicateCertificateContext(a3);
      if ( a4 )
      {
        *a4 = v4;
        v4 = 0;
      }
    }
  }
  else
  {
    v10 = 87;
  }
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeClientCertConfig(v4);
    ZtFreeClientCertConfig((LPVOID *)lpMem);
  }
  else
  {
    DnsFreeZtClientCertConfig(v4);
    DnsFreeZtClientCertConfig(lpMem);
  }
  lpMem = 0;
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0xFu, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180012284  mov     r11, rsp
0x180012287  push    rbx
0x180012288  push    rbp
0x180012289  push    rsi
0x18001228a  push    rdi
0x18001228b  push    r13
0x18001228d  push    r14
0x18001228f  push    r15
0x180012291  sub     rsp, 50h
0x180012295  mov     rax, cs:__security_cookie
0x18001229c  xor     rax, rsp
0x18001229f  mov     [rsp+88h+var_40], rax
0x1800122a4  xor     esi, esi
0x1800122a6  movsxd  rbp, ecx
0x1800122a9  xor     r15d, r15d
0x1800122ac  mov     qword ptr [r11-48h], 0
0x1800122b4  mov     rdi, r9
0x1800122b7  mov     r14, r8
0x1800122ba  mov     rbx, rdx
0x1800122bd  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800122c4  jz      short loc_1800122DA
0x1800122c6  mov     [r11-58h], r9
0x1800122ca  mov     r9d, ebp
0x1800122cd  mov     [r11-60h], r8
0x1800122d1  mov     [r11-68h], rdx
0x1800122d5  call    WPP_SF_dqqqq
0x1800122da  test    rdi, rdi
0x1800122dd  jz      short loc_1800122E2
0x1800122df  mov     [rdi], rsi
0x1800122e2  test    rbx, rbx
0x1800122e5  jnz     short loc_1800122F1
0x1800122e7  mov     ebx, 57h ; 'W'
0x1800122ec  jmp     loc_180012382
0x1800122f1  cmp     ebp, 1
0x1800122f4  ja      short loc_1800122E7
0x1800122f6  lea     rdx, [rsp+88h+lpMem]
0x1800122fb  mov     rcx, rbx
0x1800122fe  call    ZtCopyClientCertConfig
0x180012303  mov     ebx, eax
0x180012305  test    eax, eax
0x180012307  jnz     short loc_180012360
0x180012309  mov     rdx, [rsp+88h+lpMem]
0x18001230e  lea     r13, cs:180000000h
0x180012315  mov     rsi, rva g_rgpZtClientCerts[r13+rbp*8]
0x18001231d  mov     [rsp+88h+lpMem], r15
0x180012322  mov     r15, rva g_rgpZtClientCertContext[r13+rbp*8]
0x18001232a  mov     rva g_rgpZtClientCerts[r13+rbp*8], rdx
0x180012332  mov     rva g_rgpZtClientCertContext[r13+rbp*8], 0
0x18001233e  test    r14, r14
0x180012341  jz      short loc_180012354
0x180012343  mov     rcx, r14; pCertContext
0x180012346  call    cs:__imp_CertDuplicateCertificateContext
0x18001234c  mov     rva g_rgpZtClientCertContext[r13+rbp*8], rax
0x180012354  test    rdi, rdi
0x180012357  jz      short loc_180012382
0x180012359  mov     [rdi], rsi
0x18001235c  xor     esi, esi
0x18001235e  jmp     short loc_180012382
0x180012360  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012367  jz      short loc_180012382
0x180012369  mov     edx, 0Eh
0x18001236e  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x180012375  mov     ecx, 40Bh
0x18001237a  mov     r9d, eax
0x18001237d  call    WPP_SF_d
0x180012382  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180012389  mov     rcx, rsi; lpMem
0x18001238c  jz      short loc_18001239F
0x18001238e  call    ZtFreeClientCertConfig
0x180012393  mov     rcx, [rsp+88h+lpMem]; lpMem
0x180012398  call    ZtFreeClientCertConfig
0x18001239d  jmp     short loc_1800123B0
0x18001239f  call    cs:__imp_DnsFreeZtClientCertConfig
0x1800123a5  mov     rcx, [rsp+88h+lpMem]
0x1800123aa  call    cs:__imp_DnsFreeZtClientCertConfig
0x1800123b0  mov     [rsp+88h+lpMem], 0
0x1800123b9  test    r15, r15
0x1800123bc  jz      short loc_1800123C7
0x1800123be  mov     rcx, r15; pCertContext
0x1800123c1  call    cs:__imp_CertFreeCertificateContext
0x1800123c7  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800123ce  jz      short loc_1800123E9
0x1800123d0  mov     edx, 0Fh
0x1800123d5  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x1800123dc  mov     ecx, 40Bh
0x1800123e1  mov     r9d, ebx
0x1800123e4  call    WPP_SF_d
0x1800123e9  mov     eax, ebx
0x1800123eb  mov     rcx, [rsp+88h+var_40]
0x1800123f0  xor     rcx, rsp; StackCookie
0x1800123f3  call    __security_check_cookie
0x1800123f8  add     rsp, 50h
0x1800123fc  pop     r15
0x1800123fe  pop     r14
0x180012400  pop     r13
0x180012402  pop     rdi
0x180012403  pop     rsi
0x180012404  pop     rbp
0x180012405  pop     rbx
0x180012406  retn
```
