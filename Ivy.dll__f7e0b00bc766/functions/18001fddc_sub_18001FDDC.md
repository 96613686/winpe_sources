# sub_18001FDDC

- ea: `0x18001fddc`
- end: `0x18001ffc8`
- name: `sub_18001FDDC`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800200c0`

## callees

- `0x180011ac4`
- `0x180011ae8`
- `0x180015c38`
- `0x18001fddc`
- `0x180020090`
- `0x18016ea56`
- `0x18016eaf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001fe77`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001fe77`

## string_xrefs

- `0x18001fee3`: `http://www.microsoft.com/ivycharting/properties/gauge_rangecount_uint32`

## pseudocode

```c
__int64 __fastcall sub_18001FDDC(__int64 a1, double a2, double a3)
{
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdi
  __int64 result; // rax
  char Reserved; // [rsp+20h] [rbp-38h]

  if ( dclass(a2) <= 0 && dclass(a3) <= 0 && a2 >= a3 )
  {
    sub_180015C38(508641922);
    try
    {
      sub_180020090(508641922, 0, "startValue must be strictly less than endValue.");
    }
    catch ( ... )
    {
      result = sub_180001030();
      if ( *(_QWORD *)(result + 80) )
      {
        if ( *(_DWORD *)(result + 88) <= 3u )
        {
          result = sub_180001030();
          if ( *(_QWORD *)(result + 80) )
            return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64 *))(**(_QWORD **)(result + 80)
                                                                                           + 16LL))(
                     *(_QWORD *)(result + 80),
                     3,
                     1,
                     508641889,
                     &qword_1801AB2B8);
        }
      }
      return result;
    }
  }
  v4 = a1 + *(int *)(*(_QWORD *)(a1 - 8) + 4LL) - 8LL;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
  v6 = v5;
  if ( v5 >= 6 )
  {
    sub_180011AE8(508641921, &qword_1801AB2B8);
    sub_180011AC4(508641921, "rangeIndex out of bounds.");
  }
  if ( v5 >= 6uLL )
    invoke_watson(0, 0, 0, 0, 0);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, wchar_t *))(**(_QWORD **)(a1 - 16) + 312LL))(
          *(_QWORD *)(a1 - 16),
          0,
          off_1801ADC50[v5]) )
  {
    sub_180011AE8(508641920, &qword_1801AB2B8);
    sub_180011AC4(508641920, "SetProperty() failed.");
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, wchar_t *))(**(_QWORD **)(a1 - 16) + 312LL))(
          *(_QWORD *)(a1 - 16),
          0,
          off_1801ADC20[v6]) )
  {
    sub_180011AE8(508641891, &qword_1801AB2B8);
    sub_180011AC4(508641891, "SetProperty() failed.");
  }
  Reserved = 1;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, char))(**(_QWORD **)(a1 - 16) + 328LL))(
             *(_QWORD *)(a1 - 16),
             0,
             L"http://www.microsoft.com/ivycharting/properties/gauge_rangecount_uint32",
             (unsigned int)(v6 + 1),
             Reserved);
  if ( !(_BYTE)result )
  {
    sub_180011AE8(508641890, &qword_1801AB2B8);
    sub_180011AC4(508641890, "SetProperty() failed.");
  }
  return result;
}

```

## disassembly

```asm
0x18001fddc  mov     rax, rsp
0x18001fddf  mov     [rax+8], rbx
0x18001fde3  mov     [rax+10h], rsi
0x18001fde7  mov     [rax+18h], rdi
0x18001fdeb  mov     [rax+20h], r14
0x18001fdef  push    r15
0x18001fdf1  sub     rsp, 50h
0x18001fdf5  movaps  xmmword ptr [rax-18h], xmm6
0x18001fdf9  movaps  xmmword ptr [rax-28h], xmm7
0x18001fdfd  movaps  xmm7, xmm2
0x18001fe00  movaps  xmm6, xmm1
0x18001fe03  mov     rbx, rcx
0x18001fe06  movaps  xmm0, xmm1; X
0x18001fe09  call    _dclass
0x18001fe0e  xor     r14d, r14d
0x18001fe11  test    ax, ax
0x18001fe14  jg      short loc_18001FE2D
0x18001fe16  movaps  xmm0, xmm7; X
0x18001fe19  call    _dclass
0x18001fe1e  test    ax, ax
0x18001fe21  jg      short loc_18001FE2D
0x18001fe23  comisd  xmm6, xmm7
0x18001fe27  jnb     loc_18001FF26
0x18001fe2d  mov     rax, [rbx-8]
0x18001fe31  movsxd  rcx, dword ptr [rax+4]
0x18001fe35  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001fe39  add     rcx, rbx
0x18001fe3c  mov     rax, [rcx]
0x18001fe3f  mov     rax, [rax+30h]
0x18001fe43  call    cs:__guard_dispatch_icall_fptr
0x18001fe49  mov     edi, eax
0x18001fe4b  cmp     eax, 6
0x18001fe4e  jnb     loc_18001FF42
0x18001fe54  mov     rcx, [rbx-10h]
0x18001fe58  mov     rax, [rcx]
0x18001fe5b  mov     rax, [rax+138h]
0x18001fe62  cmp     rdi, 6
0x18001fe66  jb      short loc_18001FE7E
0x18001fe68  mov     qword ptr [rsp+58h+Reserved], r14; Reserved
0x18001fe6d  xor     r9d, r9d; LineNo
0x18001fe70  xor     r8d, r8d; FileName
0x18001fe73  xor     edx, edx; FunctionName
0x18001fe75  xor     ecx, ecx; Expression
0x18001fe77  call    cs:_invoke_watson
0x18001fe7e  lea     r15, __ImageBase
0x18001fe85  mov     [rsp+58h+Reserved], 1
0x18001fe8a  movaps  xmm3, xmm6
0x18001fe8d  mov     r8, ds:rva off_1801ADC50[r15+rdi*8]; "http://www.microsoft.com/ivycharting/pr"... ...
0x18001fe95  xor     edx, edx
0x18001fe97  call    cs:__guard_dispatch_icall_fptr
0x18001fe9d  test    al, al
0x18001fe9f  jz      loc_18001FF63
0x18001fea5  mov     rcx, [rbx-10h]
0x18001fea9  mov     rax, [rcx]
0x18001feac  mov     [rsp+58h+Reserved], 1
0x18001feb1  movaps  xmm3, xmm7
0x18001feb4  mov     r8, ds:rva off_1801ADC20[r15+rdi*8]; "http://www.microsoft.com/ivycharting/pr"... ...
0x18001febc  xor     edx, edx
0x18001febe  mov     rax, [rax+138h]
0x18001fec5  call    cs:__guard_dispatch_icall_fptr
0x18001fecb  test    al, al
0x18001fecd  jz      loc_18001FF84
0x18001fed3  mov     rcx, [rbx-10h]
0x18001fed7  mov     rax, [rcx]
0x18001feda  lea     r9d, [rdi+1]
0x18001fede  mov     [rsp+58h+Reserved], 1
0x18001fee3  lea     r8, aHttpWwwMicroso_0; "http://www.microsoft.com/ivycharting/pr"...
0x18001feea  xor     edx, edx
0x18001feec  mov     rax, [rax+148h]
0x18001fef3  call    cs:__guard_dispatch_icall_fptr
0x18001fef9  test    al, al
0x18001fefb  jz      loc_18001FFA5
0x18001ff01  mov     rbx, [rsp+58h+arg_0]
0x18001ff06  mov     rsi, [rsp+58h+arg_8]
0x18001ff0b  mov     rdi, [rsp+58h+arg_10]
0x18001ff10  mov     r14, [rsp+58h+arg_18]
0x18001ff15  movaps  xmm6, [rsp+58h+var_18]
0x18001ff1a  movaps  xmm7, [rsp+58h+var_28]
0x18001ff1f  add     rsp, 50h
0x18001ff23  pop     r15
0x18001ff25  retn
0x18001ff26  mov     ebx, 1E514282h
0x18001ff2b  mov     ecx, ebx
0x18001ff2d  call    sub_180015C38
0x18001ff32  lea     r8, aStartvalueMust; "startValue must be strictly less than e"...
0x18001ff39  xor     edx, edx
0x18001ff3b  mov     ecx, ebx
0x18001ff3d  call    sub_180020090
0x18001ff42  lea     rdx, qword_1801AB2B8
0x18001ff49  mov     ebx, 1E514281h
0x18001ff4e  mov     ecx, ebx
0x18001ff50  call    sub_180011AE8
0x18001ff55  lea     rdx, aRangeindexOutO; "rangeIndex out of bounds."
0x18001ff5c  mov     ecx, ebx
0x18001ff5e  call    sub_180011AC4
0x18001ff63  lea     rdx, qword_1801AB2B8
0x18001ff6a  mov     ebx, 1E514280h
0x18001ff6f  mov     ecx, ebx
0x18001ff71  call    sub_180011AE8
0x18001ff76  lea     rdx, aSetpropertyFai; "SetProperty() failed."
0x18001ff7d  mov     ecx, ebx
0x18001ff7f  call    sub_180011AC4
0x18001ff84  lea     rdx, qword_1801AB2B8
0x18001ff8b  mov     ebx, 1E514263h
0x18001ff90  mov     ecx, ebx
0x18001ff92  call    sub_180011AE8
0x18001ff97  lea     rdx, aSetpropertyFai; "SetProperty() failed."
0x18001ff9e  mov     ecx, ebx
0x18001ffa0  call    sub_180011AC4
0x18001ffa5  lea     rdx, qword_1801AB2B8
0x18001ffac  mov     ebx, 1E514262h
0x18001ffb1  mov     ecx, ebx
0x18001ffb3  call    sub_180011AE8
0x18001ffb8  lea     rdx, aSetpropertyFai; "SetProperty() failed."
0x18001ffbf  mov     ecx, ebx
0x18001ffc1  call    sub_180011AC4
```
