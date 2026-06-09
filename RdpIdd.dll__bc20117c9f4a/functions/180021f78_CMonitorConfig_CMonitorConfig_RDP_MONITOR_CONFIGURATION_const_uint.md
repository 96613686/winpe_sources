# CMonitorConfig::CMonitorConfig(_RDP_MONITOR_CONFIGURATION * const,uint)

- ea: `0x180021f78`
- end: `0x180022598`
- name: `??0CMonitorConfig@@QEAA@QEAU_RDP_MONITOR_CONFIGURATION@@I@Z`
- size: `1568`
- prototype: `CMonitorConfig *__fastcall(CMonitorConfig *__hidden this, struct _RDP_MONITOR_CONFIGURATION *const, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18001a860`

## callees

- `0x180007b2c`
- `0x180007b38`
- `0x1800089f0`
- `0x180011584`
- `0x18001dd70`
- `0x18001ddbc`
- `0x180021b50`
- `0x180021c8c`
- `0x180021f78`
- `0x1800228a8`
- `0x180022990`

## string_xrefs

- `0x180022079`: `Unexpected RDP_MONITORCONFIG structures detected`
- `0x180022091`: `onecoreuap\termsrv\rdp_bin\win\rdpidd\monitorconfig.cpp`
- `0x180022245`: `onecoreuap\termsrv\rdp_bin\win\rdpidd\monitorconfig.cpp`
- `0x180022454`: `Unable to move to RDP_MONITORCONFIG_STRUCT_HEADER because buffer is too small`
- `0x18002240a`: `RDP_MONITORCONFIG_STRUCT_HEADER structure has invalid size %d`
- `0x18002242f`: `Unable to cast to RDP_MONITORCONFIG_MODE because buffer is too small`
- `0x180022578`: `Unable to cast to RDP_MONITORCONFIG_DISPLAY_MODE because buffer is too small`
- `0x180022553`: `Unable to cast to RDP_MONITORCONFIG_SCALE_FACTOR because buffer is too small`
- `0x1800222cb`: `Physical size cannot be updated`
- `0x18002252e`: `Unable to cast to RDP_MONITORCONFIG_PHYSICAL_SIZE because buffer is too small`
- `0x180022509`: `Unable to cast to RDP_MONITORCONFIG_COLORIMETRY because buffer is too small`
- `0x1800224e4`: `Unable to cast to RDP_MONITORCONFIG_SDR_WHITE_LEVEL because buffer is too small`
- `0x180022161`: `Monitor description cannot be updated`
- `0x1800224c2`: `Unable to cast to RDP_MONITORCONFIG_MONITOR_DESCRIPTION because buffer is too small`
- `0x18002210c`: `Container info cannot be updated`
- `0x180022479`: `Unable to cast to RDP_MONITORCONFIG_CONTAINER_INFO because buffer is too small`
- `0x1800224a8`: `Unsupported MONITORCONFIG structure type`
- `0x1800223e1`: `Unable to move to next RDP_MONITORCONFIG_STRUCT_HEADER because buffer is too small`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CMonitorConfig *__fastcall CMonitorConfig::CMonitorConfig(
        CMonitorConfig *this,
        struct _RDP_MONITOR_CONFIGURATION *const a2,
        int a3)
{
  char *v5; // r15
  _OWORD *v6; // rbp
  int v7; // ecx
  unsigned int v8; // r12d
  unsigned int *i; // rsi
  unsigned int v10; // ebx
  size_t v11; // rbp
  char *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r15
  unsigned __int64 v15; // rcx
  size_t v16; // rax
  size_t v17; // rbx
  _OWORD *v18; // rdx
  unsigned int v20; // eax
  char *v21; // [rsp+28h] [rbp-50h]
  char *v22; // [rsp+28h] [rbp-50h]
  const char *v23; // [rsp+30h] [rbp-48h]
  const char *v24; // [rsp+30h] [rbp-48h]
  const char *v25; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_DWORD *)this = a3;
  *(_OWORD *)((char *)this + 4) = 0;
  *(_QWORD *)((char *)this + 20) = 0;
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 8) = -1;
  *(_OWORD *)((char *)this + 36) = 0;
  v5 = (char *)this + 56;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_OWORD *)this + 8) = 0;
  *((_OWORD *)this + 9) = 0;
  v6 = (_OWORD *)((char *)this + 160);
  memset_0((char *)this + 160, 0, 0x4Cu);
  *(_QWORD *)((char *)this + 236) = 0;
  *((_DWORD *)this + 61) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *(_OWORD *)((char *)this + 264) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  v7 = *(_DWORD *)a2;
  *(_OWORD *)((char *)this + 36) = *(_OWORD *)((char *)a2 + 8);
  if ( !*((_QWORD *)a2 + 1) && !*((_DWORD *)a2 + 4) )
    *((_DWORD *)this + 8) = *((_DWORD *)a2 + 5);
  v8 = v7 - 24;
  if ( v7 != 24 )
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
      (const char *)0x80070057LL,
      *((_DWORD *)a2 + 1) == 3,
      (bool)"Unexpected RDP_MONITORCONFIG structures detected",
      v23);
    if ( v8 < 8 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
        (const char *)0xC0000023LL,
        (int)"Unable to move to RDP_MONITORCONFIG_STRUCT_HEADER because buffer is too small",
        v21);
    for ( i = (unsigned int *)((char *)a2 + 24); ; i = (unsigned int *)((char *)i + *i) )
    {
      if ( v8 < *i )
      {
        LODWORD(v21) = *i;
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
          (const char *)0xC0000023LL,
          (int)"RDP_MONITORCONFIG_STRUCT_HEADER structure has invalid size %d",
          v21);
      }
      switch ( i[1] )
      {
        case 1u:
          if ( *i != 44 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_MODE because buffer is too small",
              v21);
          v18 = (_OWORD *)*((_QWORD *)v5 + 1);
          if ( v18 == *((_OWORD **)v5 + 2) )
          {
            std::vector<_RDP_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDP_MONITORCONFIG_MODE const &>(v5, v18, i);
          }
          else
          {
            *v18 = *(_OWORD *)i;
            v18[1] = *((_OWORD *)i + 1);
            *(_OWORD *)((char *)v18 + 28) = *(_OWORD *)(i + 7);
            *((_QWORD *)v5 + 1) += 44LL;
          }
          *((_DWORD *)this + 7) |= 1u;
          break;
        case 2u:
          if ( *i != 48 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_DISPLAY_MODE because buffer is too small",
              v21);
          *((_OWORD *)this + 5) = *(_OWORD *)i;
          *((_OWORD *)this + 6) = *((_OWORD *)i + 1);
          *((_OWORD *)this + 7) = *((_OWORD *)i + 2);
          *((_DWORD *)this + 6) |= 1u;
          *((_DWORD *)this + 7) |= 2u;
          break;
        case 3u:
          if ( *i != 16 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x93,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_SCALE_FACTOR because buffer is too small",
              v21);
          *((_OWORD *)this + 8) = *(_OWORD *)i;
          *((_DWORD *)this + 6) |= 2u;
          *((_DWORD *)this + 7) |= 4u;
          break;
        case 4u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xA1,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Physical size cannot be updated",
            v24);
          if ( *i != 16 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0xA8,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_PHYSICAL_SIZE because buffer is too small",
              v21);
          *((_OWORD *)this + 9) = *(_OWORD *)i;
          *((_DWORD *)this + 6) |= 4u;
          *((_DWORD *)this + 7) |= 8u;
          break;
        case 5u:
          if ( *i != 76 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0xB7,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_COLORIMETRY because buffer is too small",
              v21);
          *v6 = *(_OWORD *)i;
          v6[1] = *((_OWORD *)i + 1);
          v6[2] = *((_OWORD *)i + 2);
          v6[3] = *((_OWORD *)i + 3);
          *(_OWORD *)((char *)v6 + 60) = *(_OWORD *)(i + 15);
          *((_DWORD *)this + 6) |= 8u;
          *((_DWORD *)this + 7) |= 0x10u;
          break;
        case 6u:
          if ( *i != 12 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0xC6,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_SDR_WHITE_LEVEL because buffer is too small",
              v21);
          *(_QWORD *)((char *)this + 236) = *(_QWORD *)i;
          *((_DWORD *)this + 61) = i[2];
          *((_DWORD *)this + 6) |= 0x10u;
          *((_DWORD *)this + 7) |= 0x20u;
          break;
        case 7u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xD4,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Monitor description cannot be updated",
            v24);
          if ( *i <= 0xC )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0xDB,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_MONITOR_DESCRIPTION because buffer is too small",
              v22);
          v10 = *i - 12;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            v10 > 0x8000,
            (bool)"Monitor description blob cannot exceed 32K",
            v25);
          v11 = v10;
          v12 = (char *)this + 280;
          v13 = *((_QWORD *)this + 35);
          v14 = *((_QWORD *)this + 36);
          v15 = v14 - v13;
          if ( v11 < v14 - v13 )
          {
            v16 = v13 + v11;
            goto LABEL_24;
          }
          if ( v11 > v15 )
          {
            if ( v11 <= *((_QWORD *)this + 37) - v13 )
            {
              v17 = v11 - v15;
              memset_0(*((void **)this + 36), 0, v11 - v15);
              v16 = v14 + v17;
              v12 = (char *)this + 280;
LABEL_24:
              *((_QWORD *)v12 + 1) = v16;
            }
            else
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 280, v11);
            }
          }
          memmove_0(*(void **)v12, i + 3, v11);
          *((_DWORD *)this + 76) = i[2];
          *((_DWORD *)this + 7) |= 0x40u;
          v5 = (char *)this + 56;
          v6 = (_OWORD *)((char *)this + 160);
          break;
        case 8u:
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
            (const char *)0x80070057LL,
            *((_DWORD *)a2 + 1) == 2,
            (bool)"Container info cannot be updated",
            v24);
          if ( *i != 32 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0xF9,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to RDP_MONITORCONFIG_CONTAINER_INFO because buffer is too small",
              v21);
          *(_OWORD *)((char *)this + 248) = *(_OWORD *)i;
          *(_OWORD *)((char *)this + 264) = *((_OWORD *)i + 1);
          *((_DWORD *)this + 7) |= 0x80u;
          break;
        default:
          v20 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
            (const char *)v20,
            (int)"Unsupported MONITORCONFIG structure type",
            v21);
      }
      v8 -= *i;
      if ( !v8 )
      {
        if ( (*((_DWORD *)this + 7) & 0x40) != 0 )
          CMonitorConfig::ParseMonitorDescription(this);
        CMonitorConfig::ValidateAndFixMonitorConfig(this);
        return this;
      }
      if ( v8 < 8 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
          (const char *)0xC0000023LL,
          (int)"Unable to move to next RDP_MONITORCONFIG_STRUCT_HEADER because buffer is too small",
          v21);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180021f78  mov     [rsp+arg_0], rcx
0x180021f7d  push    rbx
0x180021f7e  push    rbp
0x180021f7f  push    rsi
0x180021f80  push    rdi
0x180021f81  push    r12
0x180021f83  push    r13
0x180021f85  push    r14
0x180021f87  push    r15
0x180021f89  sub     rsp, 38h
0x180021f8d  mov     r14, rdx
0x180021f90  mov     rdi, rcx
0x180021f93  mov     [rcx], r8d
0x180021f96  xorps   xmm0, xmm0
0x180021f99  xor     eax, eax
0x180021f9b  movups  xmmword ptr [rcx+4], xmm0
0x180021f9f  mov     [rcx+14h], rax
0x180021fa3  xor     esi, esi
0x180021fa5  mov     [rcx+1Ch], esi
0x180021fa8  mov     dword ptr [rcx+20h], 0FFFFFFFFh
0x180021faf  movups  xmmword ptr [rcx+24h], xmm0
0x180021fb3  lea     r15, [rcx+38h]
0x180021fb7  mov     [r15], rsi
0x180021fba  mov     [r15+8], rsi
0x180021fbe  mov     [r15+10h], rsi
0x180021fc2  movups  xmmword ptr [rcx+50h], xmm0
0x180021fc6  movups  xmmword ptr [rcx+60h], xmm0
0x180021fca  movups  xmmword ptr [rcx+70h], xmm0
0x180021fce  movups  xmmword ptr [rcx+80h], xmm0
0x180021fd5  xorps   xmm1, xmm1
0x180021fd8  movups  xmmword ptr [rcx+90h], xmm1
0x180021fdf  lea     rbp, [rcx+0A0h]
0x180021fe6  xor     edx, edx; Val
0x180021fe8  lea     r8d, [rax+4Ch]; Size
0x180021fec  mov     rcx, rbp; void *
0x180021fef  call    memset_0
0x180021ff4  xor     eax, eax
0x180021ff6  mov     [rdi+0ECh], rax
0x180021ffd  mov     [rdi+0F4h], eax
0x180022003  xorps   xmm0, xmm0
0x180022006  movups  xmmword ptr [rdi+0F8h], xmm0
0x18002200d  movups  xmmword ptr [rdi+108h], xmm0
0x180022014  lea     rbx, [rdi+118h]
0x18002201b  mov     [rbx], rsi
0x18002201e  mov     [rbx+8], rsi
0x180022022  mov     [rbx+10h], rsi
0x180022026  mov     [rdi+130h], esi
0x18002202c  mov     ecx, [r14]
0x18002202f  movups  xmm0, xmmword ptr [r14+8]
0x180022034  movdqu  xmmword ptr [rdi+24h], xmm0
0x180022039  mov     rax, cs:qword_180046EF8
0x180022040  cmp     [r14+8], eax
0x180022044  jnz     short loc_18002205F
0x180022046  mov     eax, dword ptr cs:qword_180046EF8+4
0x18002204c  cmp     [r14+0Ch], eax
0x180022050  jnz     short loc_18002205F
0x180022052  cmp     [r14+10h], esi
0x180022056  jnz     short loc_18002205F
0x180022058  mov     eax, [r14+14h]
0x18002205c  mov     [rdi+20h], eax
0x18002205f  lea     r12d, [rcx-18h]
0x180022063  test    r12d, r12d
0x180022066  jz      loc_1800223C7
0x18002206c  cmp     dword ptr [r14+4], 3
0x180022071  setz    al
0x180022074  mov     rcx, [rsp+78h]; this
0x180022079  lea     rdx, aUnexpectedRdpM; "Unexpected RDP_MONITORCONFIG structures"...
0x180022080  mov     [rsp+78h+var_50], rdx; char *
0x180022085  mov     [rsp+78h+var_58], al; char
0x180022089  mov     ebx, 80070057h
0x18002208e  mov     r9d, ebx; char *
0x180022091  lea     r13, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180022098  mov     r8, r13; unsigned int
0x18002209b  mov     edx, 51h ; 'Q'; void *
0x1800220a0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800220a5  cmp     r12d, 8
0x1800220a9  jb      loc_18002244F
0x1800220af  lea     rsi, [r14+18h]
0x1800220b3  jmp     loc_1800223A6
0x1800220b8  mov     ecx, [rsi+4]
0x1800220bb  sub     ecx, 1
0x1800220be  jz      loc_180022354
0x1800220c4  sub     ecx, 1
0x1800220c7  jz      loc_18002232A
0x1800220cd  sub     ecx, 1
0x1800220d0  jz      loc_18002230C
0x1800220d6  sub     ecx, 1
0x1800220d9  jz      loc_1800222BE
0x1800220df  sub     ecx, 1
0x1800220e2  jz      loc_180022281
0x1800220e8  sub     ecx, 1
0x1800220eb  jz      loc_180022256
0x1800220f1  sub     ecx, 1
0x1800220f4  jz      short loc_180022154
0x1800220f6  cmp     ecx, 1
0x1800220f9  jnz     loc_180022499
0x1800220ff  cmp     dword ptr [r14+4], 2
0x180022104  setz    al
0x180022107  mov     rcx, [rsp+78h]; this
0x18002210c  lea     rdx, aContainerInfoC; "Container info cannot be updated"
0x180022113  mov     [rsp+78h+var_50], rdx; char *
0x180022118  mov     [rsp+78h+var_58], al; char
0x18002211c  mov     r9d, ebx; char *
0x18002211f  mov     r8, r13; unsigned int
0x180022122  mov     edx, 0F2h; void *
0x180022127  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002212c  cmp     dword ptr [rsi], 20h ; ' '
0x18002212f  jnz     loc_180022474
0x180022135  movups  xmm0, xmmword ptr [rsi]
0x180022138  movups  xmmword ptr [rdi+0F8h], xmm0
0x18002213f  movups  xmm1, xmmword ptr [rsi+10h]
0x180022143  movups  xmmword ptr [rdi+108h], xmm1
0x18002214a  bts     dword ptr [rdi+1Ch], 7
0x18002214f  jmp     loc_180022393
0x180022154  cmp     dword ptr [r14+4], 2
0x180022159  setz    al
0x18002215c  mov     rcx, [rsp+78h]; this
0x180022161  lea     rdx, aMonitorDescrip_0; "Monitor description cannot be updated"
0x180022168  mov     [rsp+78h+var_50], rdx; char *
0x18002216d  mov     [rsp+78h+var_58], al; char
0x180022171  mov     r9d, ebx; char *
0x180022174  mov     r8, r13; unsigned int
0x180022177  mov     edx, 0D4h; void *
0x18002217c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180022181  mov     ebx, [rsi]
0x180022183  mov     rcx, [rsp+78h]; this
0x180022188  mov     r8, r13; unsigned int
0x18002218b  cmp     ebx, 0Ch
0x18002218e  jbe     loc_1800224C2
0x180022194  add     ebx, 0FFFFFFF4h
0x180022197  cmp     ebx, 8000h
0x18002219d  setnbe  al
0x1800221a0  lea     rdx, aMonitorDescrip; "Monitor description blob cannot exceed "...
0x1800221a7  mov     [rsp+78h+var_50], rdx; bool
0x1800221ac  mov     [rsp+78h+var_58], al; char
0x1800221b0  mov     r9d, 80070057h; char *
0x1800221b6  mov     edx, 0E2h; void *
0x1800221bb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800221c0  mov     ebp, ebx
0x1800221c2  lea     rbx, [rdi+118h]
0x1800221c9  mov     rdx, [rbx]
0x1800221cc  mov     r15, [rbx+8]
0x1800221d0  mov     rcx, r15
0x1800221d3  sub     rcx, rdx
0x1800221d6  cmp     rbp, rcx
0x1800221d9  jnb     short loc_1800221E1
0x1800221db  lea     rax, [rdx+rbp]
0x1800221df  jmp     short loc_18002221A
0x1800221e1  jbe     short loc_18002221E
0x1800221e3  mov     rax, [rbx+10h]
0x1800221e7  sub     rax, rdx
0x1800221ea  cmp     rbp, rax
0x1800221ed  jbe     short loc_1800221FC
0x1800221ef  mov     rdx, rbp
0x1800221f2  mov     rcx, rbx
0x1800221f5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800221fa  jmp     short loc_18002221E
0x1800221fc  mov     rbx, rbp
0x1800221ff  sub     rbx, rcx
0x180022202  mov     r8, rbx; Size
0x180022205  xor     edx, edx; Val
0x180022207  mov     rcx, r15; void *
0x18002220a  call    memset_0
0x18002220f  lea     rax, [r15+rbx]
0x180022213  lea     rbx, [rdi+118h]
0x18002221a  mov     [rbx+8], rax
0x18002221e  mov     r8, rbp; Size
0x180022221  lea     rdx, [rsi+0Ch]; Src
0x180022225  mov     rcx, [rbx]; void *
0x180022228  call    memmove_0
0x18002222d  mov     eax, [rsi+8]
0x180022230  mov     [rdi+130h], eax
0x180022236  or      dword ptr [rdi+1Ch], 40h
0x18002223a  lea     r15, [rdi+38h]
0x18002223e  lea     rbp, [rdi+0A0h]
0x180022245  lea     r13, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002224c  mov     ebx, 80070057h
0x180022251  jmp     loc_180022393
0x180022256  cmp     dword ptr [rsi], 0Ch
0x180022259  jnz     loc_1800224DF
0x18002225f  movsd   xmm0, qword ptr [rsi]
0x180022263  movsd   qword ptr [rdi+0ECh], xmm0
0x18002226b  mov     eax, [rsi+8]
0x18002226e  mov     [rdi+0F4h], eax
0x180022274  or      dword ptr [rdi+18h], 10h
0x180022278  or      dword ptr [rdi+1Ch], 20h
0x18002227c  jmp     loc_180022393
0x180022281  cmp     dword ptr [rsi], 4Ch ; 'L'
0x180022284  jnz     loc_180022504
0x18002228a  movups  xmm0, xmmword ptr [rsi]
0x18002228d  movups  xmmword ptr [rbp+0], xmm0
0x180022291  movups  xmm1, xmmword ptr [rsi+10h]
0x180022295  movups  xmmword ptr [rbp+10h], xmm1
0x180022299  movups  xmm0, xmmword ptr [rsi+20h]
0x18002229d  movups  xmmword ptr [rbp+20h], xmm0
0x1800222a1  movups  xmm1, xmmword ptr [rsi+30h]
0x1800222a5  movups  xmmword ptr [rbp+30h], xmm1
0x1800222a9  movups  xmm0, xmmword ptr [rsi+3Ch]
0x1800222ad  movups  xmmword ptr [rbp+3Ch], xmm0
0x1800222b1  or      dword ptr [rdi+18h], 8
0x1800222b5  or      dword ptr [rdi+1Ch], 10h
0x1800222b9  jmp     loc_180022393
0x1800222be  cmp     dword ptr [r14+4], 2
0x1800222c3  setz    al
0x1800222c6  mov     rcx, [rsp+78h]; this
0x1800222cb  lea     rdx, aPhysicalSizeCa; "Physical size cannot be updated"
0x1800222d2  mov     [rsp+78h+var_50], rdx; char *
0x1800222d7  mov     [rsp+78h+var_58], al; char
0x1800222db  mov     r9d, ebx; char *
0x1800222de  mov     r8, r13; unsigned int
0x1800222e1  mov     edx, 0A1h; void *
0x1800222e6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800222eb  cmp     dword ptr [rsi], 10h
0x1800222ee  jnz     loc_180022529
0x1800222f4  movups  xmm0, xmmword ptr [rsi]
0x1800222f7  movdqu  xmmword ptr [rdi+90h], xmm0
0x1800222ff  or      dword ptr [rdi+18h], 4
0x180022303  or      dword ptr [rdi+1Ch], 8
0x180022307  jmp     loc_180022393
0x18002230c  cmp     dword ptr [rsi], 10h
0x18002230f  jnz     loc_18002254E
0x180022315  movups  xmm0, xmmword ptr [rsi]
0x180022318  movdqu  xmmword ptr [rdi+80h], xmm0
0x180022320  or      dword ptr [rdi+18h], 2
0x180022324  or      dword ptr [rdi+1Ch], 4
0x180022328  jmp     short loc_180022393
0x18002232a  cmp     dword ptr [rsi], 30h ; '0'
0x18002232d  jnz     loc_180022573
0x180022333  movups  xmm0, xmmword ptr [rsi]
0x180022336  movups  xmmword ptr [rdi+50h], xmm0
0x18002233a  movups  xmm1, xmmword ptr [rsi+10h]
0x18002233e  movups  xmmword ptr [rdi+60h], xmm1
0x180022342  movups  xmm0, xmmword ptr [rsi+20h]
0x180022346  movups  xmmword ptr [rdi+70h], xmm0
0x18002234a  or      dword ptr [rdi+18h], 1
0x18002234e  or      dword ptr [rdi+1Ch], 2
0x180022352  jmp     short loc_180022393
0x180022354  cmp     dword ptr [rsi], 2Ch ; ','
0x180022357  jnz     loc_18002242A
0x18002235d  mov     rdx, [r15+8]
0x180022361  cmp     rdx, [r15+10h]
0x180022365  jz      short loc_180022384
0x180022367  movups  xmm0, xmmword ptr [rsi]
0x18002236a  movups  xmmword ptr [rdx], xmm0
0x18002236d  movups  xmm1, xmmword ptr [rsi+10h]
0x180022371  movups  xmmword ptr [rdx+10h], xmm1
0x180022375  movups  xmm0, xmmword ptr [rsi+1Ch]
0x180022379  movups  xmmword ptr [rdx+1Ch], xmm0
0x18002237d  add     qword ptr [r15+8], 2Ch ; ','
0x180022382  jmp     short loc_18002238F
0x180022384  mov     r8, rsi
0x180022387  mov     rcx, r15
0x18002238a  call    ??$_Emplace_reallocate@AEBU_RDP_MONITORCONFIG_MODE@@@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@AEAAPEAU_RDP_MONITORCONFIG_MODE@@QEAU2@AEBU2@@Z; std::vector<_RDP_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDP_MONITORCONFIG_MODE const &>(_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE const &)
0x18002238f  or      dword ptr [rdi+1Ch], 1
0x180022393  mov     eax, [rdi+1Ch]
0x180022396  sub     r12d, [rsi]
0x180022399  jz      short loc_1800223B2
0x18002239b  cmp     r12d, 8
0x18002239f  jb      short loc_1800223DC
0x1800223a1  mov     eax, [rsi]
0x1800223a3  add     rsi, rax
0x1800223a6  mov     eax, [rsi]
0x1800223a8  cmp     r12d, eax
0x1800223ab  jb      short loc_180022401
0x1800223ad  jmp     loc_1800220B8
0x1800223b2  test    al, 40h
0x1800223b4  jz      short loc_1800223BE
0x1800223b6  mov     rcx, rdi; this
0x1800223b9  call    ?ParseMonitorDescription@CMonitorConfig@@AEAAXXZ; CMonitorConfig::ParseMonitorDescription(void)
0x1800223be  mov     rcx, rdi; this
0x1800223c1  call    ?ValidateAndFixMonitorConfig@CMonitorConfig@@AEAAXXZ; CMonitorConfig::ValidateAndFixMonitorConfig(void)
0x1800223c6  nop
0x1800223c7  mov     rax, rdi
0x1800223ca  add     rsp, 38h
0x1800223ce  pop     r15
0x1800223d0  pop     r14
0x1800223d2  pop     r13
0x1800223d4  pop     r12
0x1800223d6  pop     rdi
0x1800223d7  pop     rsi
0x1800223d8  pop     rbp
0x1800223d9  pop     rbx
0x1800223da  retn
0x1800223dc  mov     rcx, [rsp+78h]; this
0x1800223e1  lea     rax, aUnableToMoveTo_1; "Unable to move to next RDP_MONITORCONFI"...
0x1800223e8  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800223ed  mov     r9d, 0C0000023h; char *
0x1800223f3  mov     r8, r13; unsigned int
0x1800223f6  mov     edx, 11Ah; void *
0x1800223fb  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180022401  mov     rcx, [rsp+78h]; this
0x180022406  mov     dword ptr [rsp+78h+var_50], eax; char *
0x18002240a  lea     rax, aRdpMonitorconf_0; "RDP_MONITORCONFIG_STRUCT_HEADER structu"...
0x180022411  mov     qword ptr [rsp+78h+var_58], rax; int
0x180022416  mov     r9d, 0C0000023h; char *
0x18002241c  mov     r8, r13; unsigned int
0x18002241f  mov     edx, 6Ah ; 'j'; void *
0x180022424  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18002242a  mov     rcx, [rsp+78h]; this
0x18002242f  lea     rax, aUnableToCastTo_14; "Unable to cast to RDP_MONITORCONFIG_MOD"...
  ... truncated ...
```
