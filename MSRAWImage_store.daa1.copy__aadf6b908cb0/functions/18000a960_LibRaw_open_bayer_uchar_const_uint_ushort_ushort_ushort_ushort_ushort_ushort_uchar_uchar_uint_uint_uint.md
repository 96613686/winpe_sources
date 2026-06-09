# LibRaw::open_bayer(uchar const *,uint,ushort,ushort,ushort,ushort,ushort,ushort,uchar,uchar,uint,uint,uint)

- ea: `0x18000a960`
- end: `0x18000aca7`
- name: `?open_bayer@LibRaw@@UEAAHPEBEIGGGGGGEEIII@Z`
- size: `839`
- prototype: `__int64 __fastcall(LibRaw *this, const unsigned __int8 *, unsigned int, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int8, unsigned __int8, char, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003044`
- `0x180006380`
- `0x18000a960`
- `0x18000d000`
- `0x18002b5b0`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall LibRaw::open_bayer(
        LibRaw *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        unsigned __int16 a9,
        unsigned __int8 a10,
        unsigned __int8 a11,
        char a12,
        unsigned int a13,
        unsigned int a14)
{
  int v14; // r14d
  LibRaw_buffer_datastream *v18; // rax
  LibRaw_buffer_datastream *v19; // rbx
  unsigned int (*v20)(void); // rax
  __int64; // rax
  int v22; // r12d
  __int16 v23; // r14
  __int16 v24; // bx
  unsigned int v25; // eax
  unsigned int v26; // r8d
  unsigned int v27; // eax
  void (__fastcall *v28)(LibRaw *__hidden); // rax

  v14 = a4;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_9;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v18 = (LibRaw_buffer_datastream *)operator new(0x20u);
    if ( v18 )
      v19 = LibRaw_buffer_datastream::LibRaw_buffer_datastream(v18, a2, a3);
    else
      v19 = 0;
    v20 = *(unsigned int (**)(void))(*(_QWORD *)v19 + 8LL);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      LibRaw::recycle(this);
       = 4294867289LL;
      __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_18000AC9D);
LABEL_28:
      ;
    }
  }
  if ( !v20() )
  {
    (**(void (__fastcall ***)(LibRaw_buffer_datastream *, __int64))v19)(v19, 1);
LABEL_9:
     = 4294867287LL;
    goto LABEL_28;
  }
  *((_QWORD *)this + 47659) = v19;
  *((_DWORD *)this + 1346) |= 1u;
  LibRaw::initdata(this);
  strcpy((char *)this + 204, "BayerDump");
  v22 = v14;
  snprintf((char *const)this + 268, 0x3Fu, "%u x %u pixels", v14, a5);
  *((_DWORD *)this + 12) = a10 >> 2;
  *((_DWORD *)this + 95336) = a10 & 2;
  *((_QWORD *)this + 47680) = 0;
  *((_WORD *)this + 9) = v14;
  *((_WORD *)this + 8) = a5;
  *((_WORD *)this + 13) = a6;
  *((_WORD *)this + 12) = a7;
  v23 = v14 - a6 - a8;
  *((_WORD *)this + 11) = v23;
  v24 = a5 - a7 - a9;
  *((_WORD *)this + 10) = v24;
  *((_DWORD *)this + 95384) = a13;
  v25 = 8 * a3 / ((unsigned int)a5 * v22);
  v26 = v25;
  *((_DWORD *)this + 95378) = v25;
  switch ( v25 )
  {
    case 8u:
      v28 = LibRaw::eight_bit_load_raw;
      LOBYTE(v26) = 8;
      goto LABEL_21;
    case 0xAu:
      if ( 3 * (a3 / a5) >= 4 * v22 )
      {
        v28 = LibRaw::android_loose_load_raw;
        LOBYTE(v26) = 10;
        goto LABEL_21;
      }
      if ( (a13 & 1) != 0 )
      {
        v28 = LibRaw::android_tight_load_raw;
        LOBYTE(v26) = 10;
        goto LABEL_21;
      }
      break;
    case 0xCu:
      break;
    case 0x10u:
      *((_WORD *)this + 190704) = (1028 * (a13 & 1)) | 0x4949;
      v27 = (a13 >> 1) & 7;
      *((_DWORD *)this + 95384) = v27;
      v26 = v26 - (a13 >> 4) - v27;
      *((_DWORD *)this + 95378) = v26;
      v28 = LibRaw::unpacked_load_raw;
LABEL_21:
      *((_QWORD *)this + 95898) = v28;
      goto LABEL_22;
    default:
LABEL_22:
      *((_DWORD *)this + 38222) = (1 << v26) - (1 << a12);
      *((_DWORD *)this + 38220) = a14;
      *((_WORD *)this + 15) = v23;
      *((_WORD *)this + 14) = v24;
      *((_DWORD *)this + 135) = 3;
      *((_DWORD *)this + 136) = (16843009 * a11)
                              | (33686018 * a11)
                              & (((16843009 * (unsigned int)a11) >> 2) & 0x22222222 | (67372036 * a11) & 0x88888888);
      *((_DWORD *)this + 132) = 1;
      *((_DWORD *)this + 38265) = 1065353216;
      *((_DWORD *)this + 38266) = 1065353216;
      *((_DWORD *)this + 38267) = 1065353216;
      *((_DWORD *)this + 38268) = 1065353216;
      strcpy((char *)this + 620, "RGBG");
      *((_DWORD *)this + 95322) = 1;
      *((_DWORD *)this + 1346) |= 2u;
       = 0;
      goto LABEL_28;
  }
  *((_DWORD *)this + 95384) = a13 | 0x80;
  v28 = LibRaw::packed_load_raw;
  goto LABEL_21;
}

```

## disassembly

```asm
0x18000a960  mov     [rsp+arg_0], rcx
0x18000a965  push    rsi
0x18000a966  push    rdi
0x18000a967  push    r12
0x18000a969  push    r14
0x18000a96b  push    r15
0x18000a96d  sub     rsp, 40h
0x18000a971  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000a97a  mov     [rsp+68h+arg_10], rbx
0x18000a982  movzx   r14d, r9w
0x18000a986  mov     esi, r8d
0x18000a989  mov     rbx, rdx
0x18000a98c  mov     rdi, rcx
0x18000a98f  lea     rax, [rdx-1]
0x18000a993  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a997  ja      short loc_18000A9E8
0x18000a999  mov     ecx, 20h ; ' '; Size
0x18000a99e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9a3  mov     [rsp+68h+arg_8], rax
0x18000a9a8  test    rax, rax
0x18000a9ab  jz      short loc_18000A9C0
0x18000a9ad  mov     r8d, esi; unsigned __int64
0x18000a9b0  mov     rdx, rbx; void *
0x18000a9b3  mov     rcx, rax; this
0x18000a9b6  call    ??0LibRaw_buffer_datastream@@QEAA@PEBX_K@Z; LibRaw_buffer_datastream::LibRaw_buffer_datastream(void const *,unsigned __int64)
0x18000a9bb  mov     rbx, rax
0x18000a9be  jmp     short loc_18000A9C2
0x18000a9c0  xor     ebx, ebx
0x18000a9c2  mov     rax, [rbx]
0x18000a9c5  mov     rcx, rbx
0x18000a9c8  mov     rax, [rax+8]
0x18000a9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d1  test    eax, eax
0x18000a9d3  jnz     short loc_18000AA02
0x18000a9d5  mov     rax, [rbx]
0x18000a9d8  mov     edx, 1
0x18000a9dd  mov     rcx, rbx
0x18000a9e0  mov     rax, [rax]
0x18000a9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e8  mov     eax, 0FFFE7957h
0x18000a9ed  mov     rbx, [rsp+68h+arg_10]
0x18000a9f5  add     rsp, 40h
0x18000a9f9  pop     r15
0x18000a9fb  pop     r14
0x18000a9fd  pop     r12
0x18000a9ff  pop     rdi
0x18000aa00  pop     rsi
0x18000aa01  retn
0x18000aa02  mov     [rdi+5D158h], rbx
0x18000aa09  or      dword ptr [rdi+1508h], 1
0x18000aa10  mov     rcx, rdi; this
0x18000aa13  call    ?initdata@LibRaw@@IEAAXXZ; LibRaw::initdata(void)
0x18000aa18  movsd   xmm0, qword ptr cs:aBayerdump; "BayerDump"
0x18000aa20  movsd   qword ptr [rdi+0CCh], xmm0
0x18000aa28  movzx   eax, word ptr cs:aBayerdump+8; "p"
0x18000aa2f  mov     [rdi+0D4h], ax
0x18000aa36  movzx   ebx, [rsp+68h+arg_20]
0x18000aa3e  mov     r15d, ebx
0x18000aa41  mov     r12d, r14d
0x18000aa44  lea     rcx, [rdi+10Ch]; Buffer
0x18000aa4b  mov     [rsp+68h+var_48], ebx
0x18000aa4f  mov     r9d, r14d
0x18000aa52  lea     r8, Format; "%u x %u pixels"
0x18000aa59  mov     edx, 3Fh ; '?'; BufferCount
0x18000aa5e  call    _snprintf
0x18000aa63  movzx   ecx, [rsp+68h+arg_48]
0x18000aa6b  mov     eax, ecx
0x18000aa6d  shr     eax, 2
0x18000aa70  mov     [rdi+30h], eax
0x18000aa73  and     ecx, 2
0x18000aa76  mov     [rdi+5D1A0h], ecx
0x18000aa7c  mov     qword ptr [rdi+5D200h], 0
0x18000aa87  mov     [rdi+12h], r14w
0x18000aa8c  mov     [rdi+10h], bx
0x18000aa90  movzx   eax, [rsp+68h+arg_28]
0x18000aa98  mov     [rdi+1Ah], ax
0x18000aa9c  movzx   ecx, [rsp+68h+arg_30]
0x18000aaa4  mov     [rdi+18h], cx
0x18000aaa8  sub     r14w, ax
0x18000aaac  sub     r14w, [rsp+68h+arg_38]
0x18000aab5  mov     [rdi+16h], r14w
0x18000aaba  sub     bx, cx
0x18000aabd  sub     bx, [rsp+68h+arg_40]
0x18000aac5  mov     [rdi+14h], bx
0x18000aac9  movzx   r10d, [rsp+68h+arg_50]
0x18000aad2  imul    r11d, r10d, 1010101h
0x18000aad9  mov     r9d, [rsp+68h+arg_60]
0x18000aae1  mov     [rdi+5D260h], r9d
0x18000aae8  mov     ecx, r12d
0x18000aaeb  imul    ecx, r15d
0x18000aaef  lea     eax, ds:0[rsi*8]
0x18000aaf6  xor     edx, edx
0x18000aaf8  div     ecx
0x18000aafa  mov     r8d, eax
0x18000aafd  mov     [rdi+5D248h], eax
0x18000ab03  cmp     eax, 8
0x18000ab06  jz      loc_18000ABBA
0x18000ab0c  cmp     eax, 0Ah
0x18000ab0f  jz      short loc_18000AB6B
0x18000ab11  cmp     eax, 0Ch
0x18000ab14  jz      loc_18000ABA5
0x18000ab1a  cmp     eax, 10h
0x18000ab1d  jnz     loc_18000ABCE
0x18000ab23  movzx   ecx, r9w
0x18000ab27  and     cx, 1
0x18000ab2b  mov     eax, 404h
0x18000ab30  cwde
0x18000ab31  movsx   edx, cx
0x18000ab34  imul    edx, eax
0x18000ab37  or      dx, 4949h
0x18000ab3c  mov     [rdi+5D1E0h], dx
0x18000ab43  mov     eax, r9d
0x18000ab46  shr     eax, 1
0x18000ab48  and     eax, 7
0x18000ab4b  mov     [rdi+5D260h], eax
0x18000ab51  shr     r9d, 4
0x18000ab55  sub     r8d, r9d
0x18000ab58  sub     r8d, eax
0x18000ab5b  mov     [rdi+5D248h], r8d
0x18000ab62  lea     rax, ?unpacked_load_raw@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw(void)
0x18000ab69  jmp     short loc_18000ABC7
0x18000ab6b  xor     edx, edx
0x18000ab6d  mov     eax, esi
0x18000ab6f  div     r15d
0x18000ab72  lea     ecx, [rax+rax*2]
0x18000ab75  lea     eax, ds:0[r12*4]
0x18000ab7d  cmp     ecx, eax
0x18000ab7f  jb      short loc_18000AB90
0x18000ab81  lea     rax, ?android_loose_load_raw@LibRaw@@IEAAXXZ; LibRaw::android_loose_load_raw(void)
0x18000ab88  mov     r8d, 0Ah
0x18000ab8e  jmp     short loc_18000ABC7
0x18000ab90  test    r9b, 1
0x18000ab94  jz      short loc_18000ABA5
0x18000ab96  lea     rax, ?android_tight_load_raw@LibRaw@@IEAAXXZ; LibRaw::android_tight_load_raw(void)
0x18000ab9d  mov     r8d, 0Ah
0x18000aba3  jmp     short loc_18000ABC7
0x18000aba5  bts     r9d, 7
0x18000abaa  mov     [rdi+5D260h], r9d
0x18000abb1  lea     rax, ?packed_load_raw@LibRaw@@IEAAXXZ; LibRaw::packed_load_raw(void)
0x18000abb8  jmp     short loc_18000ABC7
0x18000abba  lea     rax, ?eight_bit_load_raw@LibRaw@@IEAAXXZ; LibRaw::eight_bit_load_raw(void)
0x18000abc1  mov     r8d, 8
0x18000abc7  mov     [rdi+0BB4D0h], rax
0x18000abce  mov     ecx, r8d
0x18000abd1  mov     edx, 1
0x18000abd6  shl     edx, cl
0x18000abd8  mov     ecx, dword ptr [rsp+68h+arg_58]
0x18000abdf  mov     eax, 1
0x18000abe4  shl     eax, cl
0x18000abe6  sub     edx, eax
0x18000abe8  mov     [rdi+25538h], edx
0x18000abee  mov     eax, [rsp+68h+arg_68]
0x18000abf5  mov     [rdi+25530h], eax
0x18000abfb  mov     [rdi+1Eh], r14w
0x18000ac00  mov     [rdi+1Ch], bx
0x18000ac04  mov     dword ptr [rdi+21Ch], 3
0x18000ac0e  imul    ecx, r10d, 4040404h
0x18000ac15  and     ecx, 88888888h
0x18000ac1b  mov     eax, r11d
0x18000ac1e  shr     eax, 2
0x18000ac21  and     eax, 22222222h
0x18000ac26  or      ecx, eax
0x18000ac28  imul    eax, r10d, 2020202h
0x18000ac2f  and     ecx, eax
0x18000ac31  or      ecx, r11d
0x18000ac34  mov     [rdi+220h], ecx
0x18000ac3a  mov     dword ptr [rdi+210h], 1
0x18000ac44  mov     dword ptr [rdi+255E4h], 3F800000h
0x18000ac4e  mov     dword ptr [rdi+255E8h], 3F800000h
0x18000ac58  mov     dword ptr [rdi+255ECh], 3F800000h
0x18000ac62  mov     dword ptr [rdi+255F0h], 3F800000h
0x18000ac6c  mov     eax, dword ptr cs:Source; "RGBG"
0x18000ac72  mov     [rdi+26Ch], eax
0x18000ac78  movzx   eax, byte ptr cs:Source+4; ""
0x18000ac7f  mov     [rdi+270h], al
0x18000ac85  mov     dword ptr [rdi+5D168h], 1
0x18000ac8f  or      dword ptr [rdi+1508h], 2
0x18000ac96  xor     eax, eax
0x18000ac98  jmp     loc_18000A9ED
0x18000ac9d  mov     eax, 0FFFE7959h
0x18000aca2  jmp     loc_18000A9ED
```
