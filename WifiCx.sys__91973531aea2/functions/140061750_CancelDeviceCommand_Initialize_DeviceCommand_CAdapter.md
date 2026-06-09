# CancelDeviceCommand::Initialize(DeviceCommand *,CAdapter *)

- ea: `0x140061750`
- end: `0x1400619d5`
- name: `?Initialize@CancelDeviceCommand@@QEAAHPEAVDeviceCommand@@PEAVCAdapter@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CancelDeviceCommand *__hidden this, struct DeviceCommand *, struct CAdapter *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140061b6c`

## callees

- `0x14001b120`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x14003fd4c`
- `0x140061750`
- `0x1400dfd00`

## pseudocode

```c
__int64 __fastcall CancelDeviceCommand::Initialize(
        CancelDeviceCommand *this,
        struct DeviceCommand *a2,
        struct CAdapter *a3)
{
  __int128 v3; // xmm0
  DeviceCommand *v4; // rdi
  unsigned int InputBuffer; // edi
  int v7; // r9d
  unsigned __int8 *v8; // rsi
  int v10; // [rsp+30h] [rbp-49h]
  __int64 v11; // [rsp+38h] [rbp-41h]
  unsigned int v12; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v13; // [rsp+54h] [rbp-25h] BYREF
  __int64 v14; // [rsp+58h] [rbp-21h] BYREF
  int v15; // [rsp+60h] [rbp-19h]
  unsigned __int8 *v16; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int8 *v17; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v18[2]; // [rsp+78h] [rbp-1h] BYREF
  __int128 v19; // [rsp+88h] [rbp+Fh] BYREF

  v3 = *(_OWORD *)((char *)a3 + 5384);
  v18[0] = 64;
  v16 = 0;
  v18[1] = (char *)this + 184;
  v4 = a2;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v13 = 0;
  v19 = v3;
  v17 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      (_DWORD)a3,
      41,
      (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
      (char)this,
      *((_DWORD *)this + 2));
  }
  if ( !v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        42,
        (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
        (char)this,
        *((_DWORD *)this + 2));
    }
    InputBuffer = -1073741811;
    goto LABEL_24;
  }
  InputBuffer = DeviceCommand::get_InputBuffer(v4, &v12, &v16);
  if ( InputBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return InputBuffer;
    v7 = 43;
    v10 = *((_DWORD *)this + 2);
    goto LABEL_23;
  }
  LODWORD(a2) = 48;
  if ( v12 < 0x30 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        44,
        (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
        (char)this,
        *((_DWORD *)this + 2),
        48,
        v12);
    }
    InputBuffer = -1073676267;
    goto LABEL_24;
  }
  v8 = v16;
  LOWORD(v15) = *((_WORD *)v16 + 16);
  LODWORD(v14) = *(_DWORD *)v16;
  HIDWORD(v14) = *((_DWORD *)v16 + 10);
  *(_QWORD *)&v19 = v18;
  InputBuffer = GenerateWdiAbortTaskToIhv((unsigned int)&v14, 48, (unsigned int)&v19, (unsigned int)&v13, (__int64)&v17);
  if ( InputBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return InputBuffer;
    v7 = 45;
    goto LABEL_22;
  }
  InputBuffer = DeviceCommand::Initialize(this, *((_WORD *)v8 + 16), 75, v13, v17);
  if ( InputBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return InputBuffer;
    v7 = 46;
LABEL_22:
    v10 = *((_DWORD *)this + 2);
LABEL_23:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      (_DWORD)a3,
      v7,
      (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
      (char)this,
      v10);
  }
LABEL_24:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v11) = InputBuffer;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      (_DWORD)a3,
      47,
      (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
      (char)this,
      *((_DWORD *)this + 2),
      v11);
  }
  return InputBuffer;
}

```

## disassembly

```asm
0x140061750  push    rbp
0x140061752  push    rbx
0x140061753  push    rsi
0x140061754  push    rdi
0x140061755  push    r12
0x140061757  push    r14
0x140061759  push    r15
0x14006175b  lea     rbp, [rsp-27h]
0x140061760  sub     rsp, 0A0h
0x140061767  mov     rax, cs:__security_cookie
0x14006176e  xor     rax, rsp
0x140061771  mov     [rbp+57h+var_38], rax
0x140061775  movups  xmm0, xmmword ptr [r8+1508h]
0x14006177d  xor     r15d, r15d
0x140061780  mov     [rbp+57h+var_58], 40h ; '@'
0x140061788  lea     rax, [rcx+0B8h]
0x14006178f  mov     [rbp+57h+var_68], r15
0x140061793  mov     [rbp+57h+var_50], rax
0x140061797  mov     rdi, rdx
0x14006179a  xor     eax, eax
0x14006179c  mov     [rbp+57h+var_80], r15d
0x1400617a0  mov     [rbp+57h+var_78], rax
0x1400617a4  mov     rbx, rcx
0x1400617a7  mov     [rbp+57h+var_70], eax
0x1400617aa  mov     [rbp+57h+var_7C], r15d
0x1400617ae  movdqu  [rbp+57h+var_48], xmm0
0x1400617b3  mov     [rbp+57h+var_60], r15
0x1400617b7  lea     r14, WPP_RECORDER_INITIALIZED
0x1400617be  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400617c5  lea     r12, WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids
0x1400617cc  jz      short loc_140061804
0x1400617ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400617d5  cmp     byte ptr [rcx+29h], 5
0x1400617d9  jnb     short loc_1400617E2
0x1400617db  cmp     [rcx+48h], r15w
0x1400617e0  jz      short loc_140061804
0x1400617e2  mov     eax, [rbx+8]
0x1400617e5  mov     r9d, 29h ; ')'
0x1400617eb  mov     rcx, [rcx+40h]
0x1400617ef  mov     dl, 5
0x1400617f1  mov     [rsp+0D0h+var_A0], eax
0x1400617f5  mov     [rsp+0D0h+var_A8], rbx
0x1400617fa  mov     [rsp+0D0h+var_B0], r12
0x1400617ff  call    WPP_RECORDER_SF_qD
0x140061804  test    rdi, rdi
0x140061807  jnz     short loc_140061843
0x140061809  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140061810  jz      short loc_140061839
0x140061812  mov     rcx, cs:WPP_GLOBAL_Control
0x140061819  lea     r9d, [rdi+2Ah]
0x14006181d  mov     eax, [rbx+8]
0x140061820  mov     dl, 2
0x140061822  mov     [rsp+0D0h+var_A0], eax
0x140061826  mov     [rsp+0D0h+var_A8], rbx
0x14006182b  mov     rcx, [rcx+40h]
0x14006182f  mov     [rsp+0D0h+var_B0], r12
0x140061834  call    WPP_RECORDER_SF_qD
0x140061839  mov     edi, 0C000000Dh
0x14006183e  jmp     loc_140061971
0x140061843  lea     r8, [rbp+57h+var_68]; unsigned __int8 **
0x140061847  mov     rcx, rdi; this
0x14006184a  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x14006184e  call    ?get_InputBuffer@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_InputBuffer(ulong *,uchar * *)
0x140061853  mov     edi, eax
0x140061855  test    eax, eax
0x140061857  jz      short loc_140061878
0x140061859  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140061860  jz      loc_1400619B4
0x140061866  mov     ecx, [rbx+8]
0x140061869  mov     r9d, 2Bh ; '+'
0x14006186f  mov     [rsp+0D0h+var_A0], ecx
0x140061873  jmp     loc_140061955
0x140061878  mov     eax, [rbp+57h+var_80]
0x14006187b  mov     edx, 30h ; '0'
0x140061880  cmp     eax, edx
0x140061882  jnb     short loc_1400618C6
0x140061884  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006188b  jz      short loc_1400618BC
0x14006188d  mov     rcx, cs:WPP_GLOBAL_Control
0x140061894  lea     r9d, [rdx-4]
0x140061898  mov     [rsp+0D0h+var_90], eax
0x14006189c  mov     eax, [rbx+8]
0x14006189f  mov     dword ptr [rsp+0D0h+var_98], edx
0x1400618a3  mov     dl, 2
0x1400618a5  mov     rcx, [rcx+40h]
0x1400618a9  mov     [rsp+0D0h+var_A0], eax
0x1400618ad  mov     [rsp+0D0h+var_A8], rbx
0x1400618b2  mov     [rsp+0D0h+var_B0], r12
0x1400618b7  call    WPP_RECORDER_SF_qDdd
0x1400618bc  mov     edi, 0C0010015h
0x1400618c1  jmp     loc_140061971
0x1400618c6  mov     rsi, [rbp+57h+var_68]
0x1400618ca  lea     r9, [rbp+57h+var_7C]
0x1400618ce  lea     r8, [rbp+57h+var_48]
0x1400618d2  lea     rcx, [rbp+57h+var_78]
0x1400618d6  movzx   eax, word ptr [rsi+20h]
0x1400618da  mov     word ptr [rbp+57h+var_70], ax
0x1400618de  mov     eax, [rsi]
0x1400618e0  mov     dword ptr [rbp+57h+var_78], eax
0x1400618e3  mov     eax, [rsi+28h]
0x1400618e6  mov     dword ptr [rbp+57h+var_78+4], eax
0x1400618e9  lea     rax, [rbp+57h+var_58]
0x1400618ed  mov     qword ptr [rbp+57h+var_48], rax
0x1400618f1  lea     rax, [rbp+57h+var_60]
0x1400618f5  mov     [rsp+0D0h+var_B0], rax
0x1400618fa  call    GenerateWdiAbortTaskToIhv
0x1400618ff  mov     edi, eax
0x140061901  test    eax, eax
0x140061903  jz      short loc_14006191A
0x140061905  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006190c  jz      loc_1400619B4
0x140061912  mov     r9d, 2Dh ; '-'
0x140061918  jmp     short loc_14006194E
0x14006191a  mov     rax, [rbp+57h+var_60]
0x14006191e  mov     r8d, 4Bh ; 'K'; unsigned int
0x140061924  mov     r9d, [rbp+57h+var_7C]; unsigned int
0x140061928  mov     rcx, rbx; this
0x14006192b  movzx   edx, word ptr [rsi+20h]; unsigned __int16
0x14006192f  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x140061934  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x140061939  mov     edi, eax
0x14006193b  test    eax, eax
0x14006193d  jz      short loc_140061971
0x14006193f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140061946  jz      short loc_1400619B4
0x140061948  mov     r9d, 2Eh ; '.'
0x14006194e  mov     eax, [rbx+8]
0x140061951  mov     [rsp+0D0h+var_A0], eax
0x140061955  mov     rcx, cs:WPP_GLOBAL_Control
0x14006195c  mov     dl, 2
0x14006195e  mov     [rsp+0D0h+var_A8], rbx
0x140061963  mov     [rsp+0D0h+var_B0], r12
0x140061968  mov     rcx, [rcx+40h]
0x14006196c  call    WPP_RECORDER_SF_qD
0x140061971  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140061978  jz      short loc_1400619B4
0x14006197a  mov     rcx, cs:WPP_GLOBAL_Control
0x140061981  cmp     byte ptr [rcx+29h], 5
0x140061985  jnb     short loc_14006198E
0x140061987  cmp     [rcx+48h], r15w
0x14006198c  jz      short loc_1400619B4
0x14006198e  mov     eax, [rbx+8]
0x140061991  mov     r9d, 2Fh ; '/'
0x140061997  mov     rcx, [rcx+40h]
0x14006199b  mov     dl, 5
0x14006199d  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400619a1  mov     [rsp+0D0h+var_A0], eax
0x1400619a5  mov     [rsp+0D0h+var_A8], rbx
0x1400619aa  mov     [rsp+0D0h+var_B0], r12
0x1400619af  call    WPP_RECORDER_SF_qDD
0x1400619b4  mov     eax, edi
0x1400619b6  mov     rcx, [rbp+57h+var_38]
0x1400619ba  xor     rcx, rsp; StackCookie
0x1400619bd  call    __security_check_cookie
0x1400619c2  add     rsp, 0A0h
0x1400619c9  pop     r15
0x1400619cb  pop     r14
0x1400619cd  pop     r12
0x1400619cf  pop     rdi
0x1400619d0  pop     rsi
0x1400619d1  pop     rbx
0x1400619d2  pop     rbp
0x1400619d3  retn
```
