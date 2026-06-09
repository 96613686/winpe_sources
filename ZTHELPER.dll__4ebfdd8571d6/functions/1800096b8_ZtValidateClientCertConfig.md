# ZtValidateClientCertConfig

- ea: `0x1800096b8`
- end: `0x180009801`
- name: `ZtValidateClientCertConfig`
- size: `329`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004f98`
- `0x180008e40`

## callees

- `0x1800096b8`
- `0x18000d78c`
- `0x18000d82c`
- `0x180015008`
- `0x180015094`
- `0x180015268`

## pseudocode

```c
__int64 __fastcall ZtValidateClientCertConfig(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 i; // rsi
  __int64 j; // rsi
  USHORT v9; // dx

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 0xCu, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, a1);
  if ( a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
    {
      v5 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      WPP_SF_Dd(1026, 0xDu, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, a4, *(_DWORD *)a1);
      goto LABEL_25;
    }
    v6 = *(_QWORD *)(a1 + 16);
    if ( (v6 == 0) == (*(_DWORD *)(a1 + 24) == 0) )
    {
      if ( (*(_QWORD *)(a1 + 32) == 0) == (*(_DWORD *)(a1 + 40) == 0) )
      {
        v5 = 0;
        if ( v6 )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 24); i = (unsigned int)(i + 1) )
          {
            v5 = DnsZtValidateCertHash(*(_QWORD *)(a1 + 16) + 36 * i);
            if ( v5 )
              goto LABEL_25;
          }
        }
        if ( *(_QWORD *)(a1 + 32) )
        {
          for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 40); j = (unsigned int)(j + 1) )
          {
            v5 = DnsZtValidateEkus(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * j));
            if ( v5 )
              break;
          }
        }
        goto LABEL_25;
      }
      v5 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v9 = 15;
    }
    else
    {
      v5 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v9 = 14;
    }
    WPP_SF_d(1026, v9, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, 87);
  }
  else
  {
    v5 = 87;
  }
LABEL_25:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x10u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800096b8  push    rbx
0x1800096ba  push    rsi
0x1800096bb  push    rdi
0x1800096bc  push    r12
0x1800096be  push    r15
0x1800096c0  sub     rsp, 30h
0x1800096c4  mov     rbx, rcx
0x1800096c7  test    byte ptr cs:xmmword_18001F260, 4
0x1800096ce  lea     r12, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x1800096d5  mov     r15d, 402h
0x1800096db  jz      short loc_1800096F0
0x1800096dd  mov     edx, 0Ch
0x1800096e2  mov     ecx, r15d
0x1800096e5  mov     r9, rbx
0x1800096e8  mov     r8, r12
0x1800096eb  call    WPP_SF_q
0x1800096f0  test    rbx, rbx
0x1800096f3  jnz     short loc_1800096FD
0x1800096f5  lea     edi, [rbx+57h]
0x1800096f8  jmp     loc_1800097D7
0x1800096fd  mov     eax, [rbx]
0x1800096ff  cmp     eax, 1
0x180009702  jnz     loc_1800097B7
0x180009708  mov     rdx, [rbx+10h]
0x18000970c  xor     ecx, ecx
0x18000970e  cmp     [rbx+18h], ecx
0x180009711  setz    cl
0x180009714  xor     eax, eax
0x180009716  test    rdx, rdx
0x180009719  setz    al
0x18000971c  cmp     eax, ecx
0x18000971e  jnz     short loc_180009796
0x180009720  xor     ecx, ecx
0x180009722  cmp     [rbx+20h], rcx
0x180009726  setz    cl
0x180009729  xor     eax, eax
0x18000972b  cmp     [rbx+28h], eax
0x18000972e  setz    al
0x180009731  cmp     ecx, eax
0x180009733  jnz     short loc_180009783
0x180009735  xor     edi, edi
0x180009737  test    rdx, rdx
0x18000973a  jz      short loc_18000975E
0x18000973c  xor     esi, esi
0x18000973e  cmp     esi, [rbx+18h]
0x180009741  jnb     short loc_18000975E
0x180009743  mov     rax, [rbx+10h]
0x180009747  lea     rcx, [rsi+rsi*8]
0x18000974b  lea     rcx, [rax+rcx*4]
0x18000974f  call    DnsZtValidateCertHash
0x180009754  mov     edi, eax
0x180009756  test    eax, eax
0x180009758  jnz     short loc_1800097D7
0x18000975a  inc     esi
0x18000975c  jmp     short loc_18000973E
0x18000975e  cmp     qword ptr [rbx+20h], 0
0x180009763  jz      short loc_1800097D7
0x180009765  xor     esi, esi
0x180009767  cmp     esi, [rbx+28h]
0x18000976a  jnb     short loc_1800097D7
0x18000976c  mov     rcx, [rbx+20h]
0x180009770  mov     rcx, [rcx+rsi*8]
0x180009774  call    DnsZtValidateEkus
0x180009779  mov     edi, eax
0x18000977b  test    eax, eax
0x18000977d  jnz     short loc_1800097D7
0x18000977f  inc     esi
0x180009781  jmp     short loc_180009767
0x180009783  mov     edi, 57h ; 'W'
0x180009788  test    byte ptr cs:xmmword_18001F260, 4
0x18000978f  jz      short loc_1800097F3
0x180009791  lea     edx, [rdi-48h]
0x180009794  jmp     short loc_1800097A7
0x180009796  mov     edi, 57h ; 'W'
0x18000979b  test    byte ptr cs:xmmword_18001F260, 4
0x1800097a2  jz      short loc_1800097F3
0x1800097a4  lea     edx, [rdi-49h]
0x1800097a7  mov     ecx, r15d
0x1800097aa  mov     r9d, edi
0x1800097ad  mov     r8, r12
0x1800097b0  call    WPP_SF_d
0x1800097b5  jmp     short loc_1800097D7
0x1800097b7  mov     edi, 57h ; 'W'
0x1800097bc  test    byte ptr cs:xmmword_18001F260, 4
0x1800097c3  jz      short loc_1800097F3
0x1800097c5  lea     edx, [rdi-4Ah]
0x1800097c8  mov     [rsp+58h+var_38], eax
0x1800097cc  mov     ecx, r15d
0x1800097cf  mov     r8, r12
0x1800097d2  call    WPP_SF_Dd
0x1800097d7  test    byte ptr cs:xmmword_18001F260, 4
0x1800097de  jz      short loc_1800097F3
0x1800097e0  mov     edx, 10h
0x1800097e5  mov     ecx, r15d
0x1800097e8  mov     r9d, edi
0x1800097eb  mov     r8, r12
0x1800097ee  call    WPP_SF_d
0x1800097f3  mov     eax, edi
0x1800097f5  add     rsp, 30h
0x1800097f9  pop     r15
0x1800097fb  pop     r12
0x1800097fd  pop     rdi
0x1800097fe  pop     rsi
0x1800097ff  pop     rbx
0x180009800  retn
```
