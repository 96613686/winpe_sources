# GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)

- ea: `0x10040d210`
- end: `0x10040d50a`
- name: `??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z`
- size: `762`
- prototype: `GeometryDataBuilder *__fastcall(GeometryDataBuilder *__hidden this, struct GeoDataAllocator *, struct COriginalPoints *)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x10040d6d0`
- `0x10040db80`
- `0x10040ddc0`
- `0x10040de70`
- `0x10040e5c0`
- `0x10040ee80`
- `0x10040f200`
- `0x10040fad0`
- `0x1004102d0`
- `0x100415040`
- `0x100415260`
- `0x100415d10`
- `0x100416110`
- `0x1004162a0`
- `0x100418440`
- `0x100418c60`
- `0x100418d90`
- `0x1004190d0`
- `0x10041a490`
- `0x10041a990`
- `0x10041aca0`
- `0x10041bd30`
- `0x10041c700`
- `0x1004284a0`
- `0x100428800`

## callees

- `0x10040d210`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
GeometryDataBuilder *__fastcall GeometryDataBuilder::GeometryDataBuilder(
        GeometryDataBuilder *this,
        struct GeoDataAllocator *a2,
        struct COriginalPoints *a3)
{
  char *v6; // rsi
  int v7; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  unsigned __int64 v12; // [rsp+78h] [rbp+10h] BYREF
  char *v13; // [rsp+80h] [rbp+18h]

  *(_QWORD *)this = &IMglGeometrySink::`vftable';
  *(_QWORD *)this = &CGeometrySinkD::`vftable';
  *(_QWORD *)this = &GeometryDataBuilder::`vftable';
  v6 = (char *)this + 8;
  v13 = (char *)this + 8;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = 0;
  v7 = 1024;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v12) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD, __int64))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0,
          -2);
    }
    v8 = 1024;
    if ( v12 < 0x400 )
      v8 = v12;
  }
  else
  {
    v8 = 4096;
  }
  *((_DWORD *)v6 + 5) = (unsigned __int64)v8 >> 4;
  *((_DWORD *)v6 + 4) = 0;
  v13 = (char *)this + 32;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v12) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0);
    }
    v9 = 1024;
    if ( v12 < 0x400 )
      v9 = v12;
  }
  else
  {
    v9 = 4096;
  }
  *((_DWORD *)this + 13) = (unsigned __int64)v9 >> 3;
  *((_DWORD *)this + 12) = 0;
  v13 = (char *)this + 56;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 7) = 0;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v12) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0);
    }
    v10 = 1024;
    if ( v12 < 0x400 )
      v10 = v12;
  }
  else
  {
    v10 = 4096;
  }
  *((_DWORD *)this + 19) = v10 / 0xCuLL;
  *((_DWORD *)this + 18) = 0;
  v13 = (char *)this + 80;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 10) = 0;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v12) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0);
    }
    if ( v12 < 0x400 )
      v7 = v12;
  }
  else
  {
    v7 = 4096;
  }
  *((_DWORD *)this + 25) = v7;
  *((_DWORD *)this + 24) = 0;
  *((_WORD *)this + 90) = 0;
  *((_BYTE *)this + 182) = 1;
  *((_QWORD *)this + 23) = a2;
  *((_DWORD *)this + 48) = 0;
  *((_BYTE *)this + 196) = 1;
  *((_QWORD *)this + 25) = a3;
  return this;
}

```

## disassembly

```asm
0x10040d210  mov     r11, rsp
0x10040d213  mov     [r11+8], rcx
0x10040d217  push    rbp
0x10040d218  push    rsi
0x10040d219  push    rdi
0x10040d21a  push    r14
0x10040d21c  push    r15
0x10040d21e  sub     rsp, 40h
0x10040d222  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x10040d22a  mov     [r11+20h], rbx
0x10040d22e  mov     rbp, r8
0x10040d231  mov     r14, rdx
0x10040d234  mov     rbx, rcx
0x10040d237  lea     rax, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10040d23e  mov     [rcx], rax
0x10040d241  lea     rax, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x10040d248  mov     [rcx], rax
0x10040d24b  lea     rax, ??_7GeometryDataBuilder@@6B@; const GeometryDataBuilder::`vftable'
0x10040d252  mov     [rcx], rax
0x10040d255  lea     rsi, [rcx+8]
0x10040d259  mov     [r11+18h], rsi
0x10040d25d  xor     r15d, r15d
0x10040d260  mov     [rsi+8], r15
0x10040d264  mov     [rsi], r15
0x10040d267  mov     edi, 400h
0x10040d26c  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10040d273  jz      short loc_10040D2DF
0x10040d275  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10040d27c  mov     rax, [rcx]
0x10040d27f  lea     rdx, [r11+10h]
0x10040d283  call    qword ptr [rax+50h]
0x10040d286  test    eax, eax
0x10040d288  jns     short loc_10040D2CD
0x10040d28a  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r15; SOS_AutoHost g_SOSHost
0x10040d291  jz      short loc_10040D29D
0x10040d293  mov     ds:0, r15d
0x10040d29b  jmp     short loc_10040D2CD
0x10040d29d  mov     rax, ds:0
0x10040d2a5  mov     [rsp+68h+var_40], r15
0x10040d2aa  mov     [rsp+68h+var_48], 4Dh ; 'M'
0x10040d2b2  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10040d2b9  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x10040d2c0  mov     edx, 1
0x10040d2c5  xor     ecx, ecx
0x10040d2c7  call    qword ptr [rax+210h]
0x10040d2cd  mov     rax, rdi
0x10040d2d0  mov     rcx, [rsp+68h+arg_8]
0x10040d2d5  cmp     rcx, rdi
0x10040d2d8  jnb     short loc_10040D2E4
0x10040d2da  mov     rax, rcx
0x10040d2dd  jmp     short loc_10040D2E4
0x10040d2df  mov     eax, 1000h
0x10040d2e4  cdqe
0x10040d2e6  shr     rax, 4
0x10040d2ea  mov     [rsi+14h], eax
0x10040d2ed  mov     [rsi+10h], r15d
0x10040d2f1  lea     rsi, [rbx+20h]
0x10040d2f5  mov     [rsp+68h+arg_10], rsi
0x10040d2fd  mov     [rsi+8], r15
0x10040d301  mov     [rsi], r15
0x10040d304  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d30c  jz      short loc_10040D37A
0x10040d30e  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10040d315  mov     rax, [rcx]
0x10040d318  lea     rdx, [rsp+68h+arg_8]
0x10040d31d  call    qword ptr [rax+50h]
0x10040d320  test    eax, eax
0x10040d322  jns     short loc_10040D368
0x10040d324  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d32c  jz      short loc_10040D338
0x10040d32e  mov     ds:0, r15d
0x10040d336  jmp     short loc_10040D368
0x10040d338  mov     rax, ds:0
0x10040d340  mov     [rsp+68h+var_40], r15
0x10040d345  mov     [rsp+68h+var_48], 4Dh ; 'M'
0x10040d34d  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10040d354  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x10040d35b  mov     edx, 1
0x10040d360  xor     ecx, ecx
0x10040d362  call    qword ptr [rax+210h]
0x10040d368  mov     rax, rdi
0x10040d36b  mov     rcx, [rsp+68h+arg_8]
0x10040d370  cmp     rcx, rdi
0x10040d373  jnb     short loc_10040D37F
0x10040d375  mov     rax, rcx
0x10040d378  jmp     short loc_10040D37F
0x10040d37a  mov     eax, 1000h
0x10040d37f  cdqe
0x10040d381  shr     rax, 3
0x10040d385  mov     [rsi+14h], eax
0x10040d388  mov     [rsi+10h], r15d
0x10040d38c  lea     rsi, [rbx+38h]
0x10040d390  mov     [rsp+68h+arg_10], rsi
0x10040d398  mov     [rsi+8], r15
0x10040d39c  mov     [rsi], r15
0x10040d39f  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d3a7  jz      short loc_10040D415
0x10040d3a9  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10040d3b0  mov     rax, [rcx]
0x10040d3b3  lea     rdx, [rsp+68h+arg_8]
0x10040d3b8  call    qword ptr [rax+50h]
0x10040d3bb  test    eax, eax
0x10040d3bd  jns     short loc_10040D403
0x10040d3bf  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d3c7  jz      short loc_10040D3D3
0x10040d3c9  mov     ds:0, r15d
0x10040d3d1  jmp     short loc_10040D403
0x10040d3d3  mov     rax, ds:0
0x10040d3db  mov     [rsp+68h+var_40], r15
0x10040d3e0  mov     [rsp+68h+var_48], 4Dh ; 'M'
0x10040d3e8  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10040d3ef  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x10040d3f6  mov     edx, 1
0x10040d3fb  xor     ecx, ecx
0x10040d3fd  call    qword ptr [rax+210h]
0x10040d403  mov     rax, rdi
0x10040d406  mov     rcx, [rsp+68h+arg_8]
0x10040d40b  cmp     rcx, rdi
0x10040d40e  jnb     short loc_10040D41A
0x10040d410  mov     rax, rcx
0x10040d413  jmp     short loc_10040D41A
0x10040d415  mov     eax, 1000h
0x10040d41a  movsxd  rcx, eax
0x10040d41d  mov     rax, 0AAAAAAAAAAAAAAABh
0x10040d427  mul     rcx
0x10040d42a  shr     rdx, 3
0x10040d42e  mov     [rsi+14h], edx
0x10040d431  mov     [rsi+10h], r15d
0x10040d435  lea     rsi, [rbx+50h]
0x10040d439  mov     [rsp+68h+arg_10], rsi
0x10040d441  mov     [rsi+8], r15
0x10040d445  mov     [rsi], r15
0x10040d448  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d450  jz      short loc_10040D4BB
0x10040d452  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10040d459  mov     rax, [rcx]
0x10040d45c  lea     rdx, [rsp+68h+arg_8]
0x10040d461  call    qword ptr [rax+50h]
0x10040d464  test    eax, eax
0x10040d466  jns     short loc_10040D4AC
0x10040d468  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10040d470  jz      short loc_10040D47C
0x10040d472  mov     ds:0, r15d
0x10040d47a  jmp     short loc_10040D4AC
0x10040d47c  mov     rax, ds:0
0x10040d484  mov     [rsp+68h+var_40], r15
0x10040d489  mov     [rsp+68h+var_48], 4Dh ; 'M'
0x10040d491  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10040d498  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x10040d49f  mov     edx, 1
0x10040d4a4  xor     ecx, ecx
0x10040d4a6  call    qword ptr [rax+210h]
0x10040d4ac  mov     rax, [rsp+68h+arg_8]
0x10040d4b1  cmp     rax, rdi
0x10040d4b4  jnb     short loc_10040D4C0
0x10040d4b6  mov     rdi, rax
0x10040d4b9  jmp     short loc_10040D4C0
0x10040d4bb  mov     edi, 1000h
0x10040d4c0  mov     [rsi+14h], edi
0x10040d4c3  mov     [rsi+10h], r15d
0x10040d4c7  mov     word ptr [rbx+0B4h], 0
0x10040d4d0  mov     byte ptr [rbx+0B6h], 1
0x10040d4d7  mov     [rbx+0B8h], r14
0x10040d4de  mov     [rbx+0C0h], r15d
0x10040d4e5  mov     byte ptr [rbx+0C4h], 1
0x10040d4ec  mov     [rbx+0C8h], rbp
0x10040d4f3  mov     rax, rbx
0x10040d4f6  mov     rbx, [rsp+68h+arg_18]
0x10040d4fe  add     rsp, 40h
0x10040d502  pop     r15
0x10040d504  pop     r14
0x10040d506  pop     rdi
0x10040d507  pop     rsi
0x10040d508  pop     rbp
0x10040d509  retn
```
