# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::WriteBytesFromTransportStream(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)

- ea: `0x140017380`
- end: `0x1400177c2`
- name: `?WriteBytesFromTransportStream@TransportParser@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAA?AUParseStats@123456@PEAVByteReader@23456@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(__int64, __int64, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14002db70`

## callees

- `0x1400010f4`
- `0x140016a3c`
- `0x140016a90`
- `0x140016e64`
- `0x140016ed0`
- `0x140017380`
- `0x140017898`
- `0x14001adc0`
- `0x14001ae00`
- `0x14001afc0`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::WriteBytesFromTransportStream(
        __int64 a1,
        __int64 a2,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *a3)
{
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *v3; // rsi
  __int64 v6; // r11
  __int64 v7; // r10
  unsigned __int64 v8; // r8
  _BYTE *v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edx
  _BYTE *v12; // rcx
  _BYTE *v13; // rax
  __int64 v14; // rax
  __int64 v15; // r13
  __int64 v16; // rsi
  char *v17; // r13
  int v18; // ebx
  __int64 v19; // r8
  __int64 v20; // rax
  unsigned __int64 v21; // r12
  unsigned __int64 v22; // rcx
  __int64 v23; // r8
  _BYTE *v24; // r15
  unsigned __int64 v25; // rbx
  _BYTE *v26; // rdx
  size_t v27; // rbx
  size_t v28; // rax
  __int64 v29; // rdx
  unsigned __int64 v30; // r8
  __int64 v32; // [rsp+20h] [rbp-69h]
  int v33; // [rsp+30h] [rbp-59h] BYREF
  int v34; // [rsp+34h] [rbp-55h] BYREF
  __int64 v35; // [rsp+38h] [rbp-51h] BYREF
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *v36; // [rsp+40h] [rbp-49h]
  char v37[32]; // [rsp+50h] [rbp-39h] BYREF
  int *v38; // [rsp+70h] [rbp-19h]
  __int64 v39; // [rsp+78h] [rbp-11h]
  int *v40; // [rsp+80h] [rbp-9h]
  __int64 v41; // [rsp+88h] [rbp-1h]
  __int64 *v42; // [rsp+90h] [rbp+7h]
  __int64 v43; // [rsp+98h] [rbp+Fh]

  v36 = a3;
  *(_QWORD *)a2 = 0;
  v3 = a3;
  if ( *(_DWORD *)(a1 + 40) != 2 )
  {
    while ( 1 )
    {
      if ( !(*(__int64 (__fastcall **)(struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *))(*(_QWORD *)v3 + 16LL))(v3) )
        return a2;
      if ( !*(_DWORD *)(a1 + 40) )
        break;
LABEL_45:
      if ( *(_DWORD *)(a1 + 40) == 1 )
      {
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(
          (Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *)(a1 + 48),
          v3);
        if ( *(_QWORD *)(a1 + 72) == *(_QWORD *)(a1 + 80) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_557c46c806da38115779eb8769b05e8d_Traceguids, a1);
          }
          Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
            (Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *)(a1 + 48),
            *(char **)(a1 + 112),
            *(_QWORD *)(a1 + 16));
          v29 = *(_QWORD *)(a1 + 80);
          v30 = *(_QWORD *)(a1 + 72) - v29;
          if ( *(_QWORD *)(a1 + 16) < v30 )
            v30 = *(_QWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 80) = v29 + v30;
          *(_DWORD *)(a1 + 40) = 2;
        }
      }
      if ( *(_DWORD *)(a1 + 40) == 2 )
        return a2;
    }
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(
      (Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *)(a1 + 48),
      v3);
    v6 = *(_QWORD *)(a1 + 64);
    v7 = *(_QWORD *)(a1 + 80);
    v8 = *(_QWORD *)(a1 + 104);
    v9 = (_BYTE *)v8;
    v10 = v7 + v6;
    if ( *(_DWORD *)a1 == 1 )
    {
      v11 = 0;
      v12 = *(_BYTE **)(a1 + 104);
      if ( v8 >= v10 )
      {
LABEL_13:
        v14 = *(_QWORD *)(a1 + 128);
        if ( v11 == 2 )
        {
          v15 = *(_QWORD *)(a1 + 8);
          LODWORD(v16) = (_DWORD)v9 - v8;
          *(_QWORD *)(a1 + 128) = &v9[v14 - v8];
          v17 = &v9[v15];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_dq(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              WPP_557c46c806da38115779eb8769b05e8d_Traceguids,
              *(unsigned int *)(a1 + 128),
              a1);
          }
          if ( *(_DWORD *)a1 == 1 )
          {
            v18 = *((_DWORD *)qword_14001E440 + ((unsigned __int64)(unsigned __int8)v9[1] >> 4));
            if ( *(_BYTE *)(a1 + 124) )
            {
              if ( v18 != *(_DWORD *)(a1 + 120) )
              {
                ++*(_DWORD *)a2;
                if ( (unsigned int)dword_140022000 > 3 )
                {
                  v35 = *(_QWORD *)(a1 + 128);
                  if ( !*(_BYTE *)(a1 + 124) )
                    __int2c();
                  v33 = *(_DWORD *)(a1 + 120);
                  v34 = v18;
                  v42 = &v35;
                  v43 = 8;
                  v40 = &v33;
                  v41 = 4;
                  v38 = &v34;
                  v39 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(&dword_140022000, word_14001F602, 0, 0, 5, v37);
                }
              }
            }
            *(_DWORD *)(a1 + 120) = (v18 + 1) % 4;
            *(_WORD *)(a1 + 125) = *(_WORD *)((char *)&v35 + 5);
            *(_BYTE *)(a1 + 127) = HIBYTE(v35);
            *(_BYTE *)(a1 + 124) = 1;
          }
          v19 = *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8);
          *(_QWORD *)(a1 + 128) = 0;
          *(_QWORD *)(a1 + 112) = v17;
          Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
            (Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer *)(a1 + 48),
            v17,
            v19);
          v20 = *(_QWORD *)(a1 + 80);
          v21 = v10 - (_QWORD)v17;
          v22 = *(_QWORD *)(a1 + 72) - v20;
          if ( v21 < v22 )
            v22 = v21;
          *(_QWORD *)(a1 + 80) = v20 + v22;
          *(_DWORD *)(a1 + 40) = 1;
        }
        else if ( v11 == 1 )
        {
          LODWORD(v16) = (_DWORD)v9 - v8;
          *(_QWORD *)(a1 + 128) = &v9[v14 - v8];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_dq(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              WPP_557c46c806da38115779eb8769b05e8d_Traceguids,
              *(unsigned int *)(a1 + 128),
              a1);
          }
          v23 = *(_QWORD *)(a1 + 88);
          v24 = &v9[-*(_QWORD *)(a1 + 104)];
          v25 = *(_QWORD *)(a1 + 72) - v23;
          v26 = (_BYTE *)v25;
          if ( (unsigned __int64)v24 < v25 )
            v26 = v24;
          v27 = v25 - (_QWORD)v26;
          *(_QWORD *)(a1 + 88) = &v26[v23];
          memmove(*(void **)(a1 + 64), &v26[*(_QWORD *)(a1 + 64) + v23], v27);
          v28 = *(_QWORD *)(a1 + 72);
          *(_QWORD *)(a1 + 88) = 0;
          if ( v27 < v28 )
            v28 = v27;
          *(_QWORD *)(a1 + 80) = v28;
          *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 32);
        }
        else
        {
          v16 = v7 - v8 + v6;
          *(_QWORD *)(a1 + 128) = v16 + v14;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            LODWORD(v32) = *(_DWORD *)(a1 + 128);
            WPP_SF_ddq(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              v8,
              (unsigned int)(*(_DWORD *)(a1 + 80) + *(_DWORD *)(a1 + 64) - *(_DWORD *)(a1 + 104)),
              v32,
              a1);
          }
          *(_QWORD *)(a1 + 80) = 0;
        }
        *(_DWORD *)(a2 + 4) += v16;
        v3 = v36;
        goto LABEL_45;
      }
      while ( 1 )
      {
        v9 = v12;
        if ( *v12 == 1 )
        {
          v13 = v12 + 1;
          v11 = 1;
          if ( (unsigned __int64)(v12 + 1) < v10 )
          {
            v11 = 0;
            if ( (*v13 & 0xF) == 8 && *((int *)qword_14001E440 + ((unsigned __int64)(unsigned __int8)*v13 >> 4)) >= 0 )
              break;
          }
        }
        if ( (unsigned __int64)++v12 >= v10 )
          goto LABEL_13;
      }
    }
    v11 = 2;
    goto LABEL_13;
  }
  return a2;
}

```

## disassembly

```asm
0x140017380  mov     [rsp-8+arg_18], rbx
0x140017385  push    rbp
0x140017386  push    rsi
0x140017387  push    rdi
0x140017388  push    r12
0x14001738a  push    r13
0x14001738c  push    r14
0x14001738e  push    r15
0x140017390  lea     rbp, [rsp-27h]
0x140017395  sub     rsp, 0B0h
0x14001739c  mov     rax, cs:__security_cookie
0x1400173a3  xor     rax, rsp
0x1400173a6  mov     [rbp+57h+var_40], rax
0x1400173aa  xor     r13d, r13d
0x1400173ad  mov     [rbp+57h+var_A0], r8
0x1400173b1  mov     [rdx], r13
0x1400173b4  mov     rsi, r8
0x1400173b7  cmp     dword ptr [rcx+28h], 2
0x1400173bb  mov     r14, rdx
0x1400173be  mov     rdi, rcx
0x1400173c1  jz      loc_140017797
0x1400173c7  lea     rbx, WPP_GLOBAL_Control
0x1400173ce  mov     rax, [rsi]
0x1400173d1  mov     rcx, rsi
0x1400173d4  mov     rax, [rax+10h]
0x1400173d8  call    _guard_dispatch_icall
0x1400173dd  test    rax, rax
0x1400173e0  jz      loc_140017797
0x1400173e6  cmp     [rdi+28h], r13d
0x1400173ea  jnz     loc_1400176F9
0x1400173f0  lea     rcx, [rdi+30h]; this
0x1400173f4  mov     rdx, rsi; struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *
0x1400173f7  call    ?WriteBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteReader@23456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)
0x1400173fc  cmp     dword ptr [rdi], 1
0x1400173ff  mov     r11, [rdi+40h]
0x140017403  mov     r10, [rdi+50h]
0x140017407  mov     r8, [rdi+68h]
0x14001740b  mov     r15, r8
0x14001740e  lea     r12, [r10+r11]
0x140017412  jnz     short loc_140017463
0x140017414  mov     edx, r13d
0x140017417  mov     rcx, r8
0x14001741a  cmp     r8, r12
0x14001741d  jnb     short loc_140017468
0x14001741f  cmp     byte ptr [rcx], 1
0x140017422  mov     r15, rcx
0x140017425  jnz     short loc_140017459
0x140017427  lea     rax, [rcx+1]
0x14001742b  mov     edx, 1
0x140017430  cmp     rax, r12
0x140017433  jnb     short loc_140017459
0x140017435  movzx   r9d, byte ptr [rax]
0x140017439  mov     edx, r13d
0x14001743c  mov     al, r9b
0x14001743f  and     al, 0Fh
0x140017441  cmp     al, 8
0x140017443  jnz     short loc_140017459
0x140017445  mov     eax, r9d
0x140017448  lea     r9, qword_14001E440
0x14001744f  shr     rax, 4
0x140017453  cmp     [r9+rax*4], r13d
0x140017457  jge     short loc_140017463
0x140017459  inc     rcx
0x14001745c  cmp     rcx, r12
0x14001745f  jb      short loc_14001741F
0x140017461  jmp     short loc_140017468
0x140017463  mov     edx, 2
0x140017468  mov     rax, [rdi+80h]
0x14001746f  cmp     edx, 2
0x140017472  jnz     loc_1400175F4
0x140017478  mov     r13, [rdi+8]
0x14001747c  mov     rsi, r15
0x14001747f  sub     rsi, r8
0x140017482  add     rax, rsi
0x140017485  mov     [rdi+80h], rax
0x14001748c  add     r13, r15
0x14001748f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017496  cmp     rcx, rbx
0x140017499  jz      short loc_1400174C9
0x14001749b  mov     eax, [rcx+2Ch]
0x14001749e  test    al, 40h
0x1400174a0  jz      short loc_1400174C9
0x1400174a2  cmp     byte ptr [rcx+29h], 3
0x1400174a6  jb      short loc_1400174C9
0x1400174a8  mov     r9d, [rdi+80h]
0x1400174af  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x1400174b6  mov     rcx, [rcx+18h]
0x1400174ba  mov     edx, 0Eh
0x1400174bf  mov     [rsp+0E0h+var_C0], rdi
0x1400174c4  call    WPP_SF_dq
0x1400174c9  cmp     dword ptr [rdi], 1
0x1400174cc  jnz     loc_1400175A7
0x1400174d2  movzx   eax, byte ptr [r15+1]
0x1400174d7  lea     rcx, qword_14001E440
0x1400174de  shr     rax, 4
0x1400174e2  xor     r15d, r15d
0x1400174e5  mov     ebx, [rcx+rax*4]
0x1400174e8  cmp     [rdi+7Ch], r15b
0x1400174ec  jz      loc_14001757F
0x1400174f2  cmp     ebx, [rdi+78h]
0x1400174f5  jz      loc_14001757F
0x1400174fb  inc     dword ptr [r14]
0x1400174fe  mov     eax, cs:dword_140022000
0x140017504  cmp     eax, 3
0x140017507  jbe     short loc_14001757F
0x140017509  mov     rax, [rdi+80h]
0x140017510  mov     [rbp+57h+var_A8], rax
0x140017514  cmp     [rdi+7Ch], r15b
0x140017518  jnz     short loc_14001751C
0x14001751a  int     2Ch; Windows NT - assertion failure
0x14001751c  mov     eax, [rdi+78h]
0x14001751f  lea     rdx, word_14001F602
0x140017526  mov     [rbp+57h+var_B0], eax
0x140017529  lea     rcx, dword_140022000
0x140017530  lea     rax, [rbp+57h+var_A8]
0x140017534  mov     [rbp+57h+var_AC], ebx
0x140017537  mov     [rbp+57h+var_50], rax
0x14001753b  xor     r9d, r9d
0x14001753e  lea     rax, [rbp+57h+var_B0]
0x140017542  mov     [rbp+57h+var_48], 8
0x14001754a  mov     [rbp+57h+var_60], rax
0x14001754e  xor     r8d, r8d
0x140017551  lea     rax, [rbp+57h+var_AC]
0x140017555  mov     [rbp+57h+var_58], 4
0x14001755d  mov     [rbp+57h+var_70], rax
0x140017561  lea     rax, [rbp+57h+var_90]
0x140017565  mov     [rsp+0E0h+var_B8], rax
0x14001756a  mov     dword ptr [rsp+0E0h+var_C0], 5
0x140017572  mov     [rbp+57h+var_68], 4
0x14001757a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001757f  lea     eax, [rbx+1]
0x140017582  and     eax, 80000003h
0x140017587  jge     short loc_140017590
0x140017589  dec     eax
0x14001758b  or      eax, 0FFFFFFFCh
0x14001758e  inc     eax
0x140017590  mov     [rdi+78h], eax
0x140017593  movzx   eax, word ptr [rbp+57h+var_A8+5]
0x140017597  mov     [rdi+7Dh], ax
0x14001759b  mov     al, byte ptr [rbp+57h+var_A8+7]
0x14001759e  mov     [rdi+7Fh], al
0x1400175a1  mov     byte ptr [rdi+7Ch], 1
0x1400175a5  jmp     short loc_1400175AA
0x1400175a7  xor     r15d, r15d
0x1400175aa  mov     r8, [rdi+18h]
0x1400175ae  lea     rcx, [rdi+30h]; this
0x1400175b2  sub     r8, [rdi+8]; unsigned __int64
0x1400175b6  mov     rdx, r13; char *
0x1400175b9  mov     [rdi+80h], r15
0x1400175c0  mov     [rdi+70h], r13
0x1400175c4  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x1400175c9  mov     rax, [rdi+50h]
0x1400175cd  sub     r12, r13
0x1400175d0  mov     rcx, [rdi+48h]
0x1400175d4  sub     rcx, rax
0x1400175d7  cmp     r12, rcx
0x1400175da  cmovb   rcx, r12
0x1400175de  add     rcx, rax
0x1400175e1  mov     [rdi+50h], rcx
0x1400175e5  xor     r13d, r13d
0x1400175e8  mov     dword ptr [rdi+28h], 1
0x1400175ef  jmp     loc_1400176F1
0x1400175f4  cmp     edx, 1
0x1400175f7  jnz     loc_14001769A
0x1400175fd  mov     rsi, r15
0x140017600  sub     rsi, r8
0x140017603  add     rax, rsi
0x140017606  mov     [rdi+80h], rax
0x14001760d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017614  cmp     rcx, rbx
0x140017617  jz      short loc_140017647
0x140017619  mov     eax, [rcx+2Ch]
0x14001761c  test    al, 40h
0x14001761e  jz      short loc_140017647
0x140017620  cmp     byte ptr [rcx+29h], 3
0x140017624  jb      short loc_140017647
0x140017626  mov     r9d, [rdi+80h]
0x14001762d  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x140017634  mov     rcx, [rcx+18h]
0x140017638  mov     edx, 0Fh
0x14001763d  mov     [rsp+0E0h+var_C0], rdi
0x140017642  call    WPP_SF_dq
0x140017647  mov     r8, [rdi+58h]
0x14001764b  sub     r15, [rdi+68h]
0x14001764f  mov     rbx, [rdi+48h]
0x140017653  sub     rbx, r8
0x140017656  cmp     r15, rbx
0x140017659  mov     rdx, rbx
0x14001765c  cmovb   rdx, r15
0x140017660  sub     rbx, rdx
0x140017663  lea     rax, [rdx+r8]
0x140017667  mov     [rdi+58h], rax
0x14001766b  mov     rcx, [rdi+40h]; void *
0x14001766f  add     rdx, rcx
0x140017672  add     rdx, r8; Src
0x140017675  mov     r8, rbx; Size
0x140017678  call    memmove
0x14001767d  mov     rax, [rdi+48h]
0x140017681  cmp     rbx, rax
0x140017684  mov     [rdi+58h], r13
0x140017688  cmovb   rax, rbx
0x14001768c  mov     [rdi+50h], rax
0x140017690  mov     rax, [rdi+20h]
0x140017694  mov     [rdi+68h], rax
0x140017698  jmp     short loc_1400176F1
0x14001769a  sub     r10, r8
0x14001769d  lea     rsi, [r10+r11]
0x1400176a1  add     rax, rsi
0x1400176a4  mov     [rdi+80h], rax
0x1400176ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176b2  cmp     rcx, rbx
0x1400176b5  jz      short loc_1400176ED
0x1400176b7  mov     eax, [rcx+2Ch]
0x1400176ba  test    al, 40h
0x1400176bc  jz      short loc_1400176ED
0x1400176be  cmp     byte ptr [rcx+29h], 3
0x1400176c2  jb      short loc_1400176ED
0x1400176c4  mov     r9d, [rdi+40h]
0x1400176c8  mov     edx, 10h
0x1400176cd  sub     r9d, [rdi+68h]
0x1400176d1  mov     eax, [rdi+80h]
0x1400176d7  add     r9d, [rdi+50h]
0x1400176db  mov     rcx, [rcx+18h]
0x1400176df  mov     [rsp+0E0h+var_B8], rdi
0x1400176e4  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400176e8  call    WPP_SF_ddq
0x1400176ed  mov     [rdi+50h], r13
0x1400176f1  add     [r14+4], esi
0x1400176f5  mov     rsi, [rbp+57h+var_A0]
0x1400176f9  cmp     dword ptr [rdi+28h], 1
0x1400176fd  jnz     loc_140017786
0x140017703  mov     rdx, rsi; struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *
0x140017706  lea     rcx, [rdi+30h]; this
0x14001770a  call    ?WriteBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteReader@23456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)
0x14001770f  mov     rcx, [rdi+50h]
0x140017713  cmp     [rdi+48h], rcx
0x140017717  jnz     short loc_140017786
0x140017719  mov     rcx, cs:WPP_GLOBAL_Control
0x140017720  lea     rax, WPP_GLOBAL_Control
0x140017727  cmp     rcx, rax
0x14001772a  jz      short loc_140017751
0x14001772c  mov     eax, [rcx+2Ch]
0x14001772f  test    al, 40h
0x140017731  jz      short loc_140017751
0x140017733  cmp     byte ptr [rcx+29h], 5
0x140017737  jb      short loc_140017751
0x140017739  mov     rcx, [rcx+18h]
0x14001773d  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x140017744  mov     edx, 11h
0x140017749  mov     r9, rdi
0x14001774c  call    WPP_SF_q
0x140017751  mov     r8, [rdi+10h]; unsigned __int64
0x140017755  lea     rcx, [rdi+30h]; this
0x140017759  mov     rdx, [rdi+70h]; char *
0x14001775d  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x140017762  mov     rdx, [rdi+50h]
0x140017766  mov     rcx, [rdi+10h]
0x14001776a  mov     r8, [rdi+48h]
0x14001776e  sub     r8, rdx
0x140017771  cmp     rcx, r8
0x140017774  cmovb   r8, rcx
0x140017778  add     r8, rdx
0x14001777b  mov     [rdi+50h], r8
0x14001777f  mov     dword ptr [rdi+28h], 2
0x140017786  cmp     dword ptr [rdi+28h], 2
0x14001778a  lea     rbx, WPP_GLOBAL_Control
0x140017791  jnz     loc_1400173CE
0x140017797  mov     rax, r14
0x14001779a  mov     rcx, [rbp+57h+var_40]
0x14001779e  xor     rcx, rsp; StackCookie
0x1400177a1  call    __security_check_cookie
0x1400177a6  mov     rbx, [rsp+0E0h+arg_18]
0x1400177ae  add     rsp, 0B0h
0x1400177b5  pop     r15
0x1400177b7  pop     r14
0x1400177b9  pop     r13
0x1400177bb  pop     r12
0x1400177bd  pop     rdi
0x1400177be  pop     rsi
0x1400177bf  pop     rbp
0x1400177c0  retn
```
