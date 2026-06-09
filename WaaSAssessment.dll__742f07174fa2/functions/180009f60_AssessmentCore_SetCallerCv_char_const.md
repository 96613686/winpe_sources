# AssessmentCore::SetCallerCv(char const *)

- ea: `0x180009f60`
- end: `0x18000a060`
- name: `?SetCallerCv@AssessmentCore@@UEAAJPEBD@Z`
- size: `256`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009fdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009fdc`

## pseudocode

```c
__int64 __fastcall AssessmentCore::SetCallerCv(AssessmentCore *this, const char *a2)
{
  const char *v2; // r14
  const char *v4; // rax
  __int64 v5; // r8
  unsigned int v6; // edi
  unsigned int v7; // edx
  unsigned __int64 v8; // rbp
  SIZE_T v9; // rsi
  _BYTE *v10; // rax
  _BYTE *v11; // rcx
  __int64 v12; // rax
  _BYTE *v13; // rax

  v2 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = a2;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = -2147024809;
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
    return v7;
  v9 = -1;
  if ( v8 + 1 >= v8 )
    v9 = v8 + 1;
  v10 = CoTaskMemAlloc(v9);
  *((_QWORD *)this + 25) = v10;
  v11 = v10;
  if ( v8 + 1 < v8 )
  {
    return v8 + 1 < v8 ? 0x80070216 : 0;
  }
  else if ( v9 )
  {
    if ( v9 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else
    {
      v12 = 2147483646;
      do
      {
        if ( !v12 )
          break;
        if ( !*v2 )
          break;
        *v11++ = *v2++;
        --v12;
        --v9;
      }
      while ( v9 );
      v13 = v11 - 1;
      if ( v9 )
        v13 = v11;
      v6 = v9 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009f60  push    rbx
0x180009f62  push    rbp
0x180009f63  push    rsi
0x180009f64  push    rdi
0x180009f65  push    r13
0x180009f67  push    r14
0x180009f69  push    r15
0x180009f6b  sub     rsp, 20h
0x180009f6f  mov     r14, rdx
0x180009f72  mov     r13, rcx
0x180009f75  test    rdx, rdx
0x180009f78  jz      loc_18000A048
0x180009f7e  mov     ecx, 7FFFFFFFh
0x180009f83  mov     rax, rdx
0x180009f86  mov     r8d, ecx
0x180009f89  cmp     byte ptr [rax], 0
0x180009f8c  jz      short loc_180009F97
0x180009f8e  inc     rax
0x180009f91  sub     r8, 1
0x180009f95  jnz     short loc_180009F89
0x180009f97  mov     rax, r8
0x180009f9a  mov     edi, 80070057h
0x180009f9f  neg     rax
0x180009fa2  mov     rax, r8
0x180009fa5  sbb     edx, edx
0x180009fa7  sub     rcx, r8
0x180009faa  not     edx
0x180009fac  and     edx, edi
0x180009fae  neg     rax
0x180009fb1  sbb     rbp, rbp
0x180009fb4  and     rbp, rcx
0x180009fb7  test    r8, r8
0x180009fba  jz      loc_18000A04D
0x180009fc0  lea     rbx, [rbp+1]
0x180009fc4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009fc8  cmp     rbx, rbp
0x180009fcb  cmovnb  rsi, rbx
0x180009fcf  sbb     r15d, r15d
0x180009fd2  mov     rcx, rsi; cb
0x180009fd5  and     r15d, 80070216h
0x180009fdc  call    cs:__imp_CoTaskMemAlloc
0x180009fe2  mov     [r13+0C8h], rax
0x180009fe9  mov     rcx, rax
0x180009fec  cmp     rbx, rbp
0x180009fef  jb      short loc_18000A043
0x180009ff1  test    rsi, rsi
0x180009ff4  jz      short loc_18000A04F
0x180009ff6  cmp     rsi, 7FFFFFFFh
0x180009ffd  ja      short loc_18000A03E
0x180009fff  mov     eax, 7FFFFFFEh
0x18000a004  test    rax, rax
0x18000a007  jz      short loc_18000A021
0x18000a009  mov     dl, [r14]
0x18000a00c  test    dl, dl
0x18000a00e  jz      short loc_18000A021
0x18000a010  mov     [rcx], dl
0x18000a012  inc     r14
0x18000a015  inc     rcx
0x18000a018  dec     rax
0x18000a01b  sub     rsi, 1
0x18000a01f  jnz     short loc_18000A004
0x18000a021  test    rsi, rsi
0x18000a024  lea     rax, [rcx-1]
0x18000a028  cmovnz  rax, rcx
0x18000a02c  neg     rsi
0x18000a02f  sbb     edi, edi
0x18000a031  not     edi
0x18000a033  and     edi, 8007007Ah
0x18000a039  mov     byte ptr [rax], 0
0x18000a03c  jmp     short loc_18000A04F
0x18000a03e  mov     byte ptr [rax], 0
0x18000a041  jmp     short loc_18000A04F
0x18000a043  mov     edi, r15d
0x18000a046  jmp     short loc_18000A04F
0x18000a048  mov     edx, 80070057h
0x18000a04d  mov     edi, edx
0x18000a04f  mov     eax, edi
0x18000a051  add     rsp, 20h
0x18000a055  pop     r15
0x18000a057  pop     r14
0x18000a059  pop     r13
0x18000a05b  pop     rdi
0x18000a05c  pop     rsi
0x18000a05d  pop     rbp
0x18000a05e  pop     rbx
0x18000a05f  retn
```
