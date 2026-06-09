# avformat_write_header

- ea: `0x180012670`
- end: `0x18001278a`
- name: `avformat_write_header`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005290`
- `0x180012610`
- `0x180012670`
- `0x18001315c`
- `0x180013b00`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avformat_write_header(__int64 a1)
{
  unsigned int v2; // esi
  __int64 result; // rax
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax

  v2 = *(_DWORD *)(a1 + 548);
  if ( !*(_DWORD *)(a1 + 544) )
  {
    result = avformat_init_output();
    if ( (int)result < 0 )
    {
      _mm_lfence();
      return result;
    }
  }
  v4 = *(_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(v4 + 72) )
  {
    if ( (*(_BYTE *)(v4 + 44) & 1) == 0 )
    {
      v5 = *(_QWORD *)(a1 + 32);
      if ( v5 )
        avio_write_marker(v5, 0x8000000000000000uLL, 0);
    }
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 72LL))(a1);
    if ( v6 < 0 )
      goto LABEL_17;
    _mm_lfence();
    v7 = *(_QWORD *)(a1 + 32);
    if ( v7 )
    {
      v6 = *(_DWORD *)(v7 + 84);
      if ( v6 < 0 )
        goto LABEL_17;
    }
    _mm_lfence();
    sub_18001315C(a1);
  }
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 44LL) & 1) == 0 )
  {
    v8 = *(_QWORD *)(a1 + 32);
    if ( v8 )
      avio_write_marker(v8, 0x8000000000000000uLL, 3);
  }
  if ( *(_DWORD *)(a1 + 548) )
    return v2;
  v6 = sub_180013B00(a1);
  if ( v6 >= 0 )
    return v2;
LABEL_17:
  v9 = *(_QWORD *)(a1 + 16);
  if ( v9 )
  {
    v10 = *(void (__fastcall **)(__int64))(v9 + 152);
    if ( v10 )
    {
      if ( *(_DWORD *)(a1 + 544) )
        v10(a1);
    }
  }
  *(_QWORD *)(a1 + 544) = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012670  mov     [rsp+arg_0], rbx
0x180012675  mov     [rsp+arg_8], rsi
0x18001267a  push    rdi
0x18001267b  sub     rsp, 20h
0x18001267f  cmp     dword ptr [rcx+220h], 0
0x180012686  mov     rbx, rcx
0x180012689  mov     esi, [rcx+224h]
0x18001268f  jnz     short loc_1800126A2
0x180012691  call    avformat_init_output
0x180012696  test    eax, eax
0x180012698  jns     short loc_1800126A2
0x18001269a  lfence
0x18001269d  jmp     loc_18001277A
0x1800126a2  mov     rax, [rbx+10h]
0x1800126a6  cmp     qword ptr [rax+48h], 0
0x1800126ab  jz      short loc_180012703
0x1800126ad  test    byte ptr [rax+2Ch], 1
0x1800126b1  jnz     short loc_1800126CE
0x1800126b3  mov     rcx, [rbx+20h]
0x1800126b7  test    rcx, rcx
0x1800126ba  jz      short loc_1800126CE
0x1800126bc  xor     r8d, r8d
0x1800126bf  mov     rdx, 8000000000000000h
0x1800126c9  call    avio_write_marker
0x1800126ce  mov     rax, [rbx+10h]
0x1800126d2  mov     rcx, rbx
0x1800126d5  mov     rax, [rax+48h]
0x1800126d9  call    cs:__guard_dispatch_icall_fptr
0x1800126df  mov     edi, eax
0x1800126e1  test    eax, eax
0x1800126e3  js      short loc_180012742
0x1800126e5  lfence
0x1800126e8  mov     rdi, [rbx+20h]
0x1800126ec  test    rdi, rdi
0x1800126ef  jz      short loc_1800126F8
0x1800126f1  mov     edi, [rdi+54h]
0x1800126f4  test    edi, edi
0x1800126f6  js      short loc_180012742
0x1800126f8  lfence
0x1800126fb  mov     rcx, rbx
0x1800126fe  call    sub_18001315C
0x180012703  mov     rax, [rbx+10h]
0x180012707  test    byte ptr [rax+2Ch], 1
0x18001270b  jnz     short loc_18001272B
0x18001270d  mov     rcx, [rbx+20h]
0x180012711  test    rcx, rcx
0x180012714  jz      short loc_18001272B
0x180012716  mov     rdx, 8000000000000000h
0x180012720  mov     r8d, 3
0x180012726  call    avio_write_marker
0x18001272b  cmp     dword ptr [rbx+224h], 0
0x180012732  jnz     short loc_180012778
0x180012734  mov     rcx, rbx
0x180012737  call    sub_180013B00
0x18001273c  mov     edi, eax
0x18001273e  test    eax, eax
0x180012740  jns     short loc_180012778
0x180012742  mov     rax, [rbx+10h]
0x180012746  test    rax, rax
0x180012749  jz      short loc_180012769
0x18001274b  mov     rax, [rax+98h]
0x180012752  test    rax, rax
0x180012755  jz      short loc_180012769
0x180012757  cmp     dword ptr [rbx+220h], 0
0x18001275e  jz      short loc_180012769
0x180012760  mov     rcx, rbx
0x180012763  call    cs:__guard_dispatch_icall_fptr
0x180012769  mov     qword ptr [rbx+220h], 0
0x180012774  mov     eax, edi
0x180012776  jmp     short loc_18001277A
0x180012778  mov     eax, esi
0x18001277a  mov     rbx, [rsp+28h+arg_0]
0x18001277f  mov     rsi, [rsp+28h+arg_8]
0x180012784  add     rsp, 20h
0x180012788  pop     rdi
0x180012789  retn
```
