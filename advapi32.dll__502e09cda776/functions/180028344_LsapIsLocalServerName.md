# LsapIsLocalServerName

- ea: `0x180028344`
- end: `0x180028500`
- name: `LsapIsLocalServerName`
- size: `444`
- prototype: `__int64 __fastcall(size_t MaxCount, wchar_t *String2)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800281d4`
- `0x180028260`

## callees

- `0x180028344`
- `0x1800720b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180028444`
- `msvcrt!_wcsnicmp` at `0x180028497`
- `msvcrt!_wcsnicmp` at `0x1800284eb`
- `msvcrt!_wcsnicmp` at `0x180028444`
- `msvcrt!_wcsnicmp` at `0x180028497`
- `msvcrt!_wcsnicmp` at `0x1800284eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180028418`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800284bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180028418`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800284bf`

## pseudocode

```c
__int64 __fastcall LsapIsLocalServerName(size_t MaxCount, wchar_t *String2, _BYTE *a3)
{
  const wchar_t *v4; // rdi
  size_t v5; // rbx
  unsigned int v6; // r14d
  unsigned int i; // ebp
  DWORD nSize[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  nSize[0] = 261;
  *a3 = 0;
  v4 = String2;
  v5 = MaxCount;
  v6 = 0;
  if ( String2 && MaxCount && *String2 )
  {
    if ( MaxCount > 1 && *String2 == 92 && String2[1] == 92 )
    {
      v5 = MaxCount - 2;
      if ( MaxCount == 2 )
        return (unsigned int)-1073741534;
      v4 = String2 + 2;
    }
    for ( i = 0; i < 2; ++i )
    {
      if ( v5 == dword_180091E38[i] && !_wcsnicmp(off_18007AB90[i], v4, v5) )
        goto LABEL_24;
    }
    if ( v5 <= 0xF
      && GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize)
      && v5 == nSize[0]
      && !_wcsnicmp(Buffer, v4, v5) )
    {
      goto LABEL_24;
    }
    if ( v4[v5 - 1] == 46 )
      --v5;
    nSize[0] = 261;
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
    {
      if ( v5 == nSize[0] && !_wcsnicmp(Buffer, v4, v5) )
LABEL_24:
        *a3 = 1;
    }
  }
  else
  {
    *a3 = 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180028344  push    rbx
0x180028346  push    rbp
0x180028347  push    rsi
0x180028348  push    rdi
0x180028349  push    r12
0x18002834b  push    r14
0x18002834d  push    r15
0x18002834f  sub     rsp, 250h
0x180028356  mov     rax, cs:__security_cookie
0x18002835d  xor     rax, rsp
0x180028360  mov     [rsp+288h+var_48], rax
0x180028368  xor     r15d, r15d
0x18002836b  mov     [rsp+288h+nSize], 105h
0x180028373  mov     [r8], r15b
0x180028376  mov     rsi, r8
0x180028379  mov     rdi, rdx
0x18002837c  mov     rbx, rcx
0x18002837f  mov     r14d, r15d
0x180028382  test    rdx, rdx
0x180028385  jz      short loc_18002838C
0x180028387  test    rcx, rcx
0x18002838a  jnz     short loc_1800283B6
0x18002838c  mov     byte ptr [r8], 1
0x180028390  mov     eax, r14d
0x180028393  mov     rcx, [rsp+288h+var_48]
0x18002839b  xor     rcx, rsp; StackCookie
0x18002839e  call    __security_check_cookie
0x1800283a3  add     rsp, 250h
0x1800283aa  pop     r15
0x1800283ac  pop     r14
0x1800283ae  pop     r12
0x1800283b0  pop     rdi
0x1800283b1  pop     rsi
0x1800283b2  pop     rbp
0x1800283b3  pop     rbx
0x1800283b4  retn
0x1800283b6  cmp     [rdx], r15w
0x1800283ba  jz      short loc_18002838C
0x1800283bc  cmp     rbx, 1
0x1800283c0  ja      loc_18002845A
0x1800283c6  mov     ebp, r15d
0x1800283c9  lea     r12, __ImageBase
0x1800283d0  cmp     ebp, 2
0x1800283d3  jnb     short loc_1800283EC
0x1800283d5  mov     ecx, ebp
0x1800283d7  mov     eax, ds:rva dword_180091E38[r12+rcx*4]
0x1800283df  cmp     rbx, rax
0x1800283e2  jz      loc_180028489
0x1800283e8  inc     ebp
0x1800283ea  jmp     short loc_1800283D0
0x1800283ec  cmp     rbx, 0Fh
0x1800283f0  jbe     loc_1800284B3
0x1800283f6  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800283fc  jnz     short loc_180028401
0x1800283fe  dec     rbx
0x180028401  lea     r8, [rsp+288h+nSize]; nSize
0x180028406  mov     [rsp+288h+nSize], 105h
0x18002840e  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180028413  mov     ecx, 3; NameType
0x180028418  call    cs:__imp_GetComputerNameExW
0x18002841f  nop     dword ptr [rax+rax+00h]
0x180028424  test    eax, eax
0x180028426  jz      loc_180028390
0x18002842c  mov     eax, [rsp+288h+nSize]
0x180028430  cmp     rbx, rax
0x180028433  jnz     loc_180028390
0x180028439  mov     r8, rbx; MaxCount
0x18002843c  lea     rcx, [rsp+288h+Buffer]; String1
0x180028441  mov     rdx, rdi; String2
0x180028444  call    cs:__imp__wcsnicmp
0x18002844b  nop     dword ptr [rax+rax+00h]
0x180028450  test    eax, eax
0x180028452  jnz     loc_180028390
0x180028458  jmp     short loc_1800284AB
0x18002845a  cmp     word ptr [rdx], 5Ch ; '\'
0x18002845e  jnz     loc_1800283C6
0x180028464  cmp     word ptr [rdx+2], 5Ch ; '\'
0x180028469  jnz     loc_1800283C6
0x18002846f  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180028473  jnz     short loc_180028480
0x180028475  mov     r14d, 0C0000122h
0x18002847b  jmp     loc_180028390
0x180028480  add     rdi, 4
0x180028484  jmp     loc_1800283C6
0x180028489  mov     rcx, ds:rva off_18007AB90[r12+rcx*8]; String1
0x180028491  mov     r8, rbx; MaxCount
0x180028494  mov     rdx, rdi; String2
0x180028497  call    cs:__imp__wcsnicmp
0x18002849e  nop     dword ptr [rax+rax+00h]
0x1800284a3  test    eax, eax
0x1800284a5  jnz     loc_1800283E8
0x1800284ab  mov     byte ptr [rsi], 1
0x1800284ae  jmp     loc_180028390
0x1800284b3  lea     r8, [rsp+288h+nSize]; nSize
0x1800284b8  xor     ecx, ecx; NameType
0x1800284ba  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x1800284bf  call    cs:__imp_GetComputerNameExW
0x1800284c6  nop     dword ptr [rax+rax+00h]
0x1800284cb  test    eax, eax
0x1800284cd  jz      loc_1800283F6
0x1800284d3  mov     eax, [rsp+288h+nSize]
0x1800284d7  cmp     rbx, rax
0x1800284da  jnz     loc_1800283F6
0x1800284e0  mov     r8, rbx; MaxCount
0x1800284e3  lea     rcx, [rsp+288h+Buffer]; String1
0x1800284e8  mov     rdx, rdi; String2
0x1800284eb  call    cs:__imp__wcsnicmp
0x1800284f2  nop     dword ptr [rax+rax+00h]
0x1800284f7  test    eax, eax
0x1800284f9  jz      short loc_1800284AB
0x1800284fb  jmp     loc_1800283F6
```
