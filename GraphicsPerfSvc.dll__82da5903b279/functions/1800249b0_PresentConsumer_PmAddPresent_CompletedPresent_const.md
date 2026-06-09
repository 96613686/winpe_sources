# PresentConsumer::PmAddPresent(CompletedPresent const &)

- ea: `0x1800249b0`
- end: `0x180024d42`
- name: `?PmAddPresent@PresentConsumer@@UEAAJAEBUCompletedPresent@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(PresentConsumer *__hidden this, const struct CompletedPresent *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180023db8`
- `0x180023f64`
- `0x1800241b0`
- `0x1800249b0`

## pseudocode

```c
__int64 __fastcall PresentConsumer::PmAddPresent(PresentConsumer *this, const struct CompletedPresent *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // r9
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  unsigned __int64 v16; // rdx
  __int64 v17; // rax
  __int64 result; // rax
  __int128 v19; // xmm0
  unsigned __int64 *v20; // rsi
  int v21; // eax
  __int64 v22; // rdx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int64 v27; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 19) != 1 )
  {
    if ( *((_DWORD *)a2 + 19) != 2 )
      goto LABEL_8;
    v16 = *((_QWORD *)this + 10);
    v17 = *((_QWORD *)this + 41);
    if ( v17 >= (__int64)(*(_QWORD *)a2 - v16) )
      v17 = *(_QWORD *)a2 - v16;
    *((_QWORD *)this + 41) = v17;
    if ( *(_QWORD *)a2 >= v16 )
      goto LABEL_8;
    return 1901;
  }
  v4 = *((_QWORD *)this + 41);
  v5 = *((_QWORD *)this + 10);
  v6 = *(_QWORD *)a2;
  v7 = *((_QWORD *)this + 21);
  v8 = v6 - v5;
  if ( v4 >= v8 )
    v4 = v8;
  *((_QWORD *)this + 41) = v4;
  v9 = *((_QWORD *)this + 40);
  if ( v9 >= (__int64)(*((_QWORD *)a2 + 1) - v7) )
    v9 = *((_QWORD *)a2 + 1) - v7;
  *((_QWORD *)this + 40) = v9;
  if ( *(_QWORD *)a2 < v5 || *((_QWORD *)a2 + 1) < v7 )
    return 1901;
LABEL_8:
  if ( *((_QWORD *)this + 63) != -1 )
  {
    if ( *((_DWORD *)this + 6) != *((_DWORD *)a2 + 6) )
      ++*((_DWORD *)this + 7);
    if ( *((_DWORD *)this + 8) != *((_DWORD *)a2 + 10) || *((_DWORD *)this + 9) != *((_DWORD *)a2 + 11) )
      ++*((_DWORD *)this + 10);
  }
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 10);
  *((_DWORD *)this + 9) = *((_DWORD *)a2 + 11);
  *((_QWORD *)this + 62) = *((_QWORD *)a2 + 4);
  *((_DWORD *)this + 11) = *((_DWORD *)a2 + 14);
  *((_QWORD *)this + 63) = *((_QWORD *)a2 + 6);
  v10 = *((_DWORD *)a2 + 14) / *((_DWORD *)this + 217);
  v11 = (unsigned int)(*((_DWORD *)this + 216) - 1);
  if ( (unsigned int)v11 >= v10 )
    v11 = v10;
  ++*(_DWORD *)(*((_QWORD *)this + 109) + 4 * v11);
  gpm::statistics::adjacent_difference<unsigned __int64,gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToFps,gpm::statistics::nonuniform_histogram<float>>>>::operator()(
    (char *)this + 608,
    a2);
  v12 = *((_DWORD *)this + 11);
  *((_BYTE *)this + 73) = 0;
  if ( v12 != *((_DWORD *)this + 12) )
  {
    if ( *((_DWORD *)this + 12) != -1 )
      ++*((_DWORD *)this + 15);
    *((_DWORD *)this + 12) = v12;
  }
  v13 = *((_DWORD *)a2 + 19);
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
          ++*((_DWORD *)this + 5);
      }
      else
      {
        *((_OWORD *)this + 5) = *(_OWORD *)a2;
        *((_OWORD *)this + 6) = *((_OWORD *)a2 + 1);
        *((_OWORD *)this + 7) = *((_OWORD *)a2 + 2);
        *((_OWORD *)this + 8) = *((_OWORD *)a2 + 3);
        v19 = *((_OWORD *)a2 + 4);
        ++*((_DWORD *)this + 4);
        *((_OWORD *)this + 9) = v19;
      }
    }
    else
    {
      v20 = (unsigned __int64 *)((char *)a2 + 8);
      gpm::statistics::adjacent_difference<unsigned __int64,gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToFps,gpm::statistics::nonuniform_histogram<float>>>>::operator()(
        (char *)this + 512,
        (char *)a2 + 8);
      v27 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2;
      gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToMs,gpm::statistics::nonuniform_histogram<float>>>::operator()(
        (char *)this + 784,
        &v27);
      if ( (*((_BYTE *)this + 920) & 1) != 0 )
        PresentConsumer::CheckForStutter(this, *v20);
      v21 = *((_DWORD *)this + 11);
      if ( v21 != *((_DWORD *)this + 13) )
      {
        if ( *((_DWORD *)this + 13) != -1 )
          ++*((_DWORD *)this + 16);
        *((_DWORD *)this + 13) = v21;
      }
      v22 = *((_QWORD *)this + 52);
      *((_BYTE *)this + 72) = 0;
      if ( v22 || *((_QWORD *)this + 53) )
      {
        v27 = (unsigned int)((2 * (*v20 - *((_QWORD *)this + 42))
                            - *((_QWORD *)this + 54)
                            - *((_QWORD *)this + 44)
                            - v22
                            + *((_QWORD *)this + 42)) >> 1);
        gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToMs,gpm::statistics::nonuniform_histogram<float>>>::operator()(
          (char *)this + 704,
          &v27);
      }
      v23 = *((_OWORD *)this + 22);
      *((_OWORD *)this + 26) = *((_OWORD *)this + 21);
      v24 = *((_OWORD *)this + 23);
      *((_OWORD *)this + 27) = v23;
      v25 = *((_OWORD *)this + 24);
      *((_OWORD *)this + 28) = v24;
      v26 = *((_OWORD *)this + 25);
      *((_OWORD *)this + 29) = v25;
      *((_OWORD *)this + 30) = v26;
      *((_OWORD *)this + 21) = *(_OWORD *)a2;
      *((_OWORD *)this + 22) = *((_OWORD *)a2 + 1);
      *((_OWORD *)this + 23) = *((_OWORD *)a2 + 2);
      *((_OWORD *)this + 24) = *((_OWORD *)a2 + 3);
      *((_OWORD *)this + 25) = *((_OWORD *)a2 + 4);
      *((_OWORD *)this + 5) = *(_OWORD *)a2;
      *((_OWORD *)this + 6) = *((_OWORD *)a2 + 1);
      *((_OWORD *)this + 7) = *((_OWORD *)a2 + 2);
      *((_OWORD *)this + 8) = *((_OWORD *)a2 + 3);
      *((_OWORD *)this + 9) = *((_OWORD *)a2 + 4);
      *((_OWORD *)this + 10) = *(_OWORD *)a2;
      *((_OWORD *)this + 11) = *((_OWORD *)a2 + 1);
      *((_OWORD *)this + 12) = *((_OWORD *)a2 + 2);
      *((_OWORD *)this + 13) = *((_OWORD *)a2 + 3);
      *((_OWORD *)this + 14) = *((_OWORD *)a2 + 4);
    }
  }
  else
  {
    ++*((_DWORD *)this + 3);
  }
  if ( *((_BYTE *)a2 + 72) )
    ++*((_DWORD *)this + 2);
  result = 0;
  *((_OWORD *)this + 15) = *(_OWORD *)a2;
  *((_OWORD *)this + 16) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 17) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 18) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 19) = *((_OWORD *)a2 + 4);
  return result;
}

```

## disassembly

```asm
0x1800249b0  mov     [rsp+arg_0], rbx
0x1800249b5  mov     [rsp+arg_10], rsi
0x1800249ba  push    rdi
0x1800249bb  sub     rsp, 20h
0x1800249bf  cmp     dword ptr [rdx+4Ch], 1
0x1800249c3  mov     rdi, rdx
0x1800249c6  mov     rbx, rcx
0x1800249c9  jnz     loc_180024AED
0x1800249cf  mov     rax, [rcx+148h]
0x1800249d6  mov     r9, [rcx+50h]
0x1800249da  mov     r8, [rdx]
0x1800249dd  mov     rdx, [rcx+0A8h]
0x1800249e4  sub     r8, r9
0x1800249e7  cmp     rax, r8
0x1800249ea  cmovge  rax, r8
0x1800249ee  mov     [rcx+148h], rax
0x1800249f5  mov     rax, [rbx+140h]
0x1800249fc  mov     rcx, [rdi+8]
0x180024a00  sub     rcx, rdx
0x180024a03  cmp     rax, rcx
0x180024a06  cmovge  rax, rcx
0x180024a0a  mov     [rbx+140h], rax
0x180024a11  cmp     [rdi], r9
0x180024a14  jb      loc_180024B1F
0x180024a1a  cmp     [rdi+8], rdx
0x180024a1e  jb      loc_180024B1F
0x180024a24  cmp     qword ptr [rbx+1F8h], 0FFFFFFFFFFFFFFFFh
0x180024a2c  jz      short loc_180024A4C
0x180024a2e  mov     eax, [rdi+18h]
0x180024a31  cmp     [rbx+18h], eax
0x180024a34  jz      short loc_180024A39
0x180024a36  inc     dword ptr [rbx+1Ch]
0x180024a39  mov     eax, [rdi+28h]
0x180024a3c  cmp     [rbx+20h], eax
0x180024a3f  jnz     short loc_180024A49
0x180024a41  mov     eax, [rdi+2Ch]
0x180024a44  cmp     [rbx+24h], eax
0x180024a47  jz      short loc_180024A4C
0x180024a49  inc     dword ptr [rbx+28h]
0x180024a4c  mov     eax, [rdi+18h]
0x180024a4f  xor     edx, edx
0x180024a51  mov     [rbx+18h], eax
0x180024a54  mov     eax, [rdi+28h]
0x180024a57  mov     [rbx+20h], eax
0x180024a5a  mov     eax, [rdi+2Ch]
0x180024a5d  mov     [rbx+24h], eax
0x180024a60  mov     rax, [rdi+20h]
0x180024a64  mov     [rbx+1F0h], rax
0x180024a6b  mov     eax, [rdi+38h]
0x180024a6e  mov     [rbx+2Ch], eax
0x180024a71  mov     rax, [rdi+30h]
0x180024a75  mov     [rbx+1F8h], rax
0x180024a7c  mov     eax, [rdi+38h]
0x180024a7f  div     dword ptr [rbx+364h]
0x180024a85  mov     ecx, [rbx+360h]
0x180024a8b  mov     rdx, rdi
0x180024a8e  dec     ecx
0x180024a90  cmp     ecx, eax
0x180024a92  cmovnb  ecx, eax
0x180024a95  mov     rax, [rbx+368h]
0x180024a9c  inc     dword ptr [rax+rcx*4]
0x180024a9f  lea     rcx, [rbx+260h]
0x180024aa6  call    ??R?$adjacent_difference@_KU?$tee@_KU?$averages@_K@statistics@gpm@@U?$transformer@_KUTicksToFps@PresentConsumer@@U?$nonuniform_histogram@M@statistics@gpm@@@23@@statistics@gpm@@@statistics@gpm@@QEAAXAEB_K@Z; gpm::statistics::adjacent_difference<unsigned __int64,gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToFps,gpm::statistics::nonuniform_histogram<float>>>>::operator()(unsigned __int64 const &)
0x180024aab  mov     eax, [rbx+2Ch]
0x180024aae  mov     byte ptr [rbx+49h], 0
0x180024ab2  cmp     eax, [rbx+30h]
0x180024ab5  jz      short loc_180024AC3
0x180024ab7  cmp     dword ptr [rbx+30h], 0FFFFFFFFh
0x180024abb  jz      short loc_180024AC0
0x180024abd  inc     dword ptr [rbx+3Ch]
0x180024ac0  mov     [rbx+30h], eax
0x180024ac3  mov     ecx, [rdi+4Ch]
0x180024ac6  test    ecx, ecx
0x180024ac8  jz      loc_180024CEE
0x180024ace  sub     ecx, 1
0x180024ad1  jz      loc_180024B5E
0x180024ad7  sub     ecx, 1
0x180024ada  jz      short loc_180024B29
0x180024adc  cmp     ecx, 1
0x180024adf  jnz     loc_180024CF1
0x180024ae5  inc     dword ptr [rbx+14h]
0x180024ae8  jmp     loc_180024CF1
0x180024aed  cmp     dword ptr [rdx+4Ch], 2
0x180024af1  jnz     loc_180024A24
0x180024af7  mov     rdx, [rcx+50h]
0x180024afb  mov     rax, [rbx+148h]
0x180024b02  mov     rcx, [rdi]
0x180024b05  sub     rcx, rdx
0x180024b08  cmp     rax, rcx
0x180024b0b  cmovge  rax, rcx
0x180024b0f  mov     [rbx+148h], rax
0x180024b16  cmp     [rdi], rdx
0x180024b19  jnb     loc_180024A24
0x180024b1f  mov     eax, 76Dh
0x180024b24  jmp     loc_180024D32
0x180024b29  movups  xmm0, xmmword ptr [rdi]
0x180024b2c  movups  xmmword ptr [rbx+50h], xmm0
0x180024b30  movups  xmm1, xmmword ptr [rdi+10h]
0x180024b34  movups  xmmword ptr [rbx+60h], xmm1
0x180024b38  movups  xmm0, xmmword ptr [rdi+20h]
0x180024b3c  movups  xmmword ptr [rbx+70h], xmm0
0x180024b40  movups  xmm1, xmmword ptr [rdi+30h]
0x180024b44  movups  xmmword ptr [rbx+80h], xmm1
0x180024b4b  movups  xmm0, xmmword ptr [rdi+40h]
0x180024b4f  inc     dword ptr [rbx+10h]
0x180024b52  movups  xmmword ptr [rbx+90h], xmm0
0x180024b59  jmp     loc_180024CF1
0x180024b5e  lea     rsi, [rdi+8]
0x180024b62  mov     rdx, rsi
0x180024b65  lea     rcx, [rbx+200h]
0x180024b6c  call    ??R?$adjacent_difference@_KU?$tee@_KU?$averages@_K@statistics@gpm@@U?$transformer@_KUTicksToFps@PresentConsumer@@U?$nonuniform_histogram@M@statistics@gpm@@@23@@statistics@gpm@@@statistics@gpm@@QEAAXAEB_K@Z; gpm::statistics::adjacent_difference<unsigned __int64,gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToFps,gpm::statistics::nonuniform_histogram<float>>>>::operator()(unsigned __int64 const &)
0x180024b71  mov     rax, [rsi]
0x180024b74  lea     rcx, [rbx+310h]
0x180024b7b  sub     rax, [rdi]
0x180024b7e  lea     rdx, [rsp+28h+arg_8]
0x180024b83  mov     [rsp+28h+arg_8], rax
0x180024b88  call    ??R?$tee@_KU?$averages@_K@statistics@gpm@@U?$transformer@_KUTicksToMs@PresentConsumer@@U?$nonuniform_histogram@M@statistics@gpm@@@23@@statistics@gpm@@QEAAXAEB_K@Z; gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToMs,gpm::statistics::nonuniform_histogram<float>>>::operator()(unsigned __int64 const &)
0x180024b8d  test    byte ptr [rbx+398h], 1
0x180024b94  jz      short loc_180024BA1
0x180024b96  mov     rdx, [rsi]; unsigned __int64
0x180024b99  mov     rcx, rbx; this
0x180024b9c  call    ?CheckForStutter@PresentConsumer@@AEAAX_K@Z; PresentConsumer::CheckForStutter(unsigned __int64)
0x180024ba1  mov     eax, [rbx+2Ch]
0x180024ba4  cmp     eax, [rbx+34h]
0x180024ba7  jz      short loc_180024BB5
0x180024ba9  cmp     dword ptr [rbx+34h], 0FFFFFFFFh
0x180024bad  jz      short loc_180024BB2
0x180024baf  inc     dword ptr [rbx+40h]
0x180024bb2  mov     [rbx+34h], eax
0x180024bb5  mov     rdx, [rbx+1A0h]
0x180024bbc  mov     byte ptr [rbx+48h], 0
0x180024bc0  test    rdx, rdx
0x180024bc3  jnz     short loc_180024BCE
0x180024bc5  cmp     [rbx+1A8h], rdx
0x180024bcc  jz      short loc_180024C0D
0x180024bce  mov     rax, [rbx+150h]
0x180024bd5  mov     rcx, [rsi]
0x180024bd8  sub     rcx, rax
0x180024bdb  add     rcx, rcx
0x180024bde  sub     rcx, [rbx+1B0h]
0x180024be5  sub     rcx, [rbx+160h]
0x180024bec  sub     rcx, rdx
0x180024bef  lea     rdx, [rsp+28h+arg_8]
0x180024bf4  add     rax, rcx
0x180024bf7  lea     rcx, [rbx+2C0h]
0x180024bfe  shr     rax, 1
0x180024c01  mov     eax, eax
0x180024c03  mov     [rsp+28h+arg_8], rax
0x180024c08  call    ??R?$tee@_KU?$averages@_K@statistics@gpm@@U?$transformer@_KUTicksToMs@PresentConsumer@@U?$nonuniform_histogram@M@statistics@gpm@@@23@@statistics@gpm@@QEAAXAEB_K@Z; gpm::statistics::tee<unsigned __int64,gpm::statistics::averages<unsigned __int64>,gpm::statistics::transformer<unsigned __int64,PresentConsumer::TicksToMs,gpm::statistics::nonuniform_histogram<float>>>::operator()(unsigned __int64 const &)
0x180024c0d  movups  xmm0, xmmword ptr [rbx+150h]
0x180024c14  movups  xmm1, xmmword ptr [rbx+160h]
0x180024c1b  movups  xmmword ptr [rbx+1A0h], xmm0
0x180024c22  movups  xmm0, xmmword ptr [rbx+170h]
0x180024c29  movups  xmmword ptr [rbx+1B0h], xmm1
0x180024c30  movups  xmm1, xmmword ptr [rbx+180h]
0x180024c37  movups  xmmword ptr [rbx+1C0h], xmm0
0x180024c3e  movups  xmm0, xmmword ptr [rbx+190h]
0x180024c45  movups  xmmword ptr [rbx+1D0h], xmm1
0x180024c4c  movups  xmmword ptr [rbx+1E0h], xmm0
0x180024c53  movups  xmm0, xmmword ptr [rdi]
0x180024c56  movups  xmmword ptr [rbx+150h], xmm0
0x180024c5d  movups  xmm1, xmmword ptr [rdi+10h]
0x180024c61  movups  xmmword ptr [rbx+160h], xmm1
0x180024c68  movups  xmm0, xmmword ptr [rdi+20h]
0x180024c6c  movups  xmmword ptr [rbx+170h], xmm0
0x180024c73  movups  xmm1, xmmword ptr [rdi+30h]
0x180024c77  movups  xmmword ptr [rbx+180h], xmm1
0x180024c7e  movups  xmm0, xmmword ptr [rdi+40h]
0x180024c82  movups  xmmword ptr [rbx+190h], xmm0
0x180024c89  movups  xmm0, xmmword ptr [rdi]
0x180024c8c  movups  xmmword ptr [rbx+50h], xmm0
0x180024c90  movups  xmm1, xmmword ptr [rdi+10h]
0x180024c94  movups  xmmword ptr [rbx+60h], xmm1
0x180024c98  movups  xmm0, xmmword ptr [rdi+20h]
0x180024c9c  movups  xmmword ptr [rbx+70h], xmm0
0x180024ca0  movups  xmm1, xmmword ptr [rdi+30h]
0x180024ca4  movups  xmmword ptr [rbx+80h], xmm1
0x180024cab  movups  xmm0, xmmword ptr [rdi+40h]
0x180024caf  movups  xmmword ptr [rbx+90h], xmm0
0x180024cb6  movups  xmm0, xmmword ptr [rdi]
0x180024cb9  movups  xmmword ptr [rbx+0A0h], xmm0
0x180024cc0  movups  xmm1, xmmword ptr [rdi+10h]
0x180024cc4  movups  xmmword ptr [rbx+0B0h], xmm1
0x180024ccb  movups  xmm0, xmmword ptr [rdi+20h]
0x180024ccf  movups  xmmword ptr [rbx+0C0h], xmm0
0x180024cd6  movups  xmm1, xmmword ptr [rdi+30h]
0x180024cda  movups  xmmword ptr [rbx+0D0h], xmm1
0x180024ce1  movups  xmm0, xmmword ptr [rdi+40h]
0x180024ce5  movups  xmmword ptr [rbx+0E0h], xmm0
0x180024cec  jmp     short loc_180024CF1
0x180024cee  inc     dword ptr [rbx+0Ch]
0x180024cf1  cmp     byte ptr [rdi+48h], 0
0x180024cf5  jz      short loc_180024CFA
0x180024cf7  inc     dword ptr [rbx+8]
0x180024cfa  movups  xmm0, xmmword ptr [rdi]
0x180024cfd  xor     eax, eax
0x180024cff  movups  xmmword ptr [rbx+0F0h], xmm0
0x180024d06  movups  xmm1, xmmword ptr [rdi+10h]
0x180024d0a  movups  xmmword ptr [rbx+100h], xmm1
0x180024d11  movups  xmm0, xmmword ptr [rdi+20h]
0x180024d15  movups  xmmword ptr [rbx+110h], xmm0
0x180024d1c  movups  xmm1, xmmword ptr [rdi+30h]
0x180024d20  movups  xmmword ptr [rbx+120h], xmm1
0x180024d27  movups  xmm0, xmmword ptr [rdi+40h]
0x180024d2b  movups  xmmword ptr [rbx+130h], xmm0
0x180024d32  mov     rbx, [rsp+28h+arg_0]
0x180024d37  mov     rsi, [rsp+28h+arg_10]
0x180024d3c  add     rsp, 20h
0x180024d40  pop     rdi
0x180024d41  retn
```
