# Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu(int,int,uint,uint)

- ea: `0x1800422bc`
- end: `0x1800425ab`
- name: `?SendUpdateVirtualDesktopPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJHHII@Z`
- size: `751`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CDsGfxChannel *__hidden this, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003ef00`

## callees

- `0x180001114`
- `0x180006580`
- `0x1800072b0`
- `0x18000e848`
- `0x1800146bc`
- `0x1800422bc`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800422fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800422fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042323`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042323`

## string_xrefs

- `0x18004234a`: `Virtual desktop update not supported by client`
- `0x180042460`: `Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu`
- `0x180042445`: `SendUpdateVirtualDesktopPdu`
- `0x180042544`: `Failed to send RDPDSGFX_PDU_CMDID_VIRTUALDESKTOPUPDATE PDU`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu(
        RTL_SRWLOCK *this,
        int a2,
        int a3,
        int a4,
        unsigned int a5)
{
  PVOID Ptr; // rbx
  const char *v10; // r9
  __int64 result; // rax
  _QWORD *v12; // rcx
  _DWORD *v13; // r8
  unsigned int v14; // eax
  int v15; // [rsp+20h] [rbp-158h]
  char *v16; // [rsp+28h] [rbp-150h]
  const char *v17; // [rsp+30h] [rbp-148h]
  int v18; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-124h] BYREF
  int v20; // [rsp+58h] [rbp-120h] BYREF
  int v21; // [rsp+5Ch] [rbp-11Ch] BYREF
  int v22; // [rsp+60h] [rbp-118h] BYREF
  int v23; // [rsp+64h] [rbp-114h] BYREF
  _QWORD v24[3]; // [rsp+68h] [rbp-110h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+80h] [rbp-F8h] BYREF
  const char *v26; // [rsp+A0h] [rbp-D8h]
  __int64 v27; // [rsp+A8h] [rbp-D0h]
  int *v28; // [rsp+B0h] [rbp-C8h]
  __int64 v29; // [rsp+B8h] [rbp-C0h]
  const char *v30; // [rsp+C0h] [rbp-B8h]
  __int64 v31; // [rsp+C8h] [rbp-B0h]
  const char *v32; // [rsp+D0h] [rbp-A8h]
  __int64 v33; // [rsp+D8h] [rbp-A0h]
  int *v34; // [rsp+E0h] [rbp-98h]
  __int64 v35; // [rsp+E8h] [rbp-90h]
  _QWORD *v36; // [rsp+F0h] [rbp-88h]
  __int64 v37; // [rsp+F8h] [rbp-80h]
  int *v38; // [rsp+100h] [rbp-78h]
  __int64 v39; // [rsp+108h] [rbp-70h]
  int *v40; // [rsp+110h] [rbp-68h]
  __int64 v41; // [rsp+118h] [rbp-60h]
  int *v42; // [rsp+120h] [rbp-58h]
  __int64 v43; // [rsp+128h] [rbp-50h]
  unsigned int *v44; // [rsp+130h] [rbp-48h]
  __int64 v45; // [rsp+138h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  AcquireSRWLockShared(this + 15);
  try
  {
    Ptr = this[14].Ptr;
    v24[1] = Ptr;
    if ( Ptr )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
    ReleaseSRWLockShared(this + 15);
    if ( Ptr )
    {
      LOBYTE(v15) = BYTE1(this[18].Ptr) == 0;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
        (const char *)0x8000FFFFLL,
        v15,
        (bool)"Virtual desktop update not supported by client",
        v17);
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        v19 = a5;
        v20 = a4;
        v21 = a3;
        v22 = a2;
        v12 = this[19].Ptr;
        v24[0] = v12[16];
        v23 = *((_DWORD *)v12 + 34);
        v18 = 482;
        v44 = &v19;
        v45 = 4;
        v42 = &v20;
        v43 = 4;
        v40 = &v21;
        v41 = 4;
        v38 = &v22;
        v39 = 4;
        v36 = v24;
        v37 = 8;
        v34 = &v23;
        v35 = 4;
        v32 = "SendUpdateVirtualDesktopPdu";
        v33 = 28;
        v30 = "Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu";
        v31 = 60;
        v28 = &v18;
        v29 = 4;
        v26 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp";
        v27 = 70;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_1800C1058,
          (unsigned __int8 *)word_1800AFFE2,
          0,
          0,
          0xCu,
          &v25);
      }
      v13 = operator new[](0x18u);
      v24[0] = v13;
      *v13 = 24;
      v13[1] = 7;
      v13[2] = a2;
      v13[3] = a3;
      v13[4] = a4;
      v13[5] = a5;
      v14 = (*(__int64 (__fastcall **)(PVOID, __int64, _DWORD *, __int64, int, int, int, _QWORD))(*(_QWORD *)Ptr + 24LL))(
              Ptr,
              24,
              v13,
              2,
              1,
              24,
              3,
              0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
        (const char *)v14,
        (int)"Failed to send RDPDSGFX_PDU_CMDID_VIRTUALDESKTOPUPDATE PDU",
        v16);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      result = 0;
    }
    else
    {
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F9,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800422bc  mov     [rsp+arg_8], rbx
0x1800422c1  mov     [rsp+arg_10], rsi
0x1800422c6  push    rdi
0x1800422c7  push    r12
0x1800422c9  push    r13
0x1800422cb  push    r14
0x1800422cd  push    r15
0x1800422cf  sub     rsp, 150h
0x1800422d6  mov     rax, cs:__security_cookie
0x1800422dd  xor     rax, rsp
0x1800422e0  mov     [rsp+178h+var_38], rax
0x1800422e8  mov     r14d, r9d
0x1800422eb  mov     r15d, r8d
0x1800422ee  mov     r12d, edx
0x1800422f1  mov     rdi, rcx
0x1800422f4  xor     r13d, r13d
0x1800422f7  add     rcx, 78h ; 'x'; SRWLock
0x1800422fb  call    cs:__imp_AcquireSRWLockShared
0x180042301  mov     rbx, [rdi+70h]
0x180042305  mov     [rsp+178h+var_108], rbx
0x18004230a  test    rbx, rbx
0x18004230d  jz      short loc_18004231F
0x18004230f  mov     rax, [rbx]
0x180042312  mov     rcx, rbx
0x180042315  mov     rax, [rax+8]
0x180042319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004231e  nop
0x18004231f  lea     rcx, [rdi+78h]; SRWLock
0x180042323  call    cs:__imp_ReleaseSRWLockShared
0x180042329  test    rbx, rbx
0x18004232c  jnz     short loc_180042338
0x18004232e  mov     eax, 8000FFFFh
0x180042333  jmp     loc_18004257D
0x180042338  cmp     [rdi+91h], r13b
0x18004233f  setz    al
0x180042342  mov     rcx, [rsp+178h]; this
0x18004234a  lea     rdx, aVirtualDesktop; "Virtual desktop update not supported by"...
0x180042351  mov     [rsp+178h+var_150], rdx; bool
0x180042356  mov     byte ptr [rsp+178h+var_158], al; int
0x18004235a  mov     r9d, 8000FFFFh; char *
0x180042360  lea     r8, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180042367  mov     edx, 1D7h; void *
0x18004236c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180042371  mov     eax, cs:dword_1800C1058
0x180042377  mov     edx, 4
0x18004237c  cmp     eax, edx
0x18004237e  jbe     loc_1800424DB
0x180042384  mov     esi, [rsp+178h+arg_20]
0x18004238b  mov     [rsp+178h+var_124], esi
0x18004238f  mov     [rsp+178h+var_120], r14d
0x180042394  mov     [rsp+178h+var_11C], r15d
0x180042399  mov     [rsp+178h+var_118], r12d
0x18004239e  mov     rcx, [rdi+98h]
0x1800423a5  mov     rax, [rcx+80h]
0x1800423ac  mov     [rsp+178h+var_110], rax
0x1800423b1  mov     eax, [rcx+88h]
0x1800423b7  mov     [rsp+178h+var_114], eax
0x1800423bb  mov     [rsp+178h+var_128], 1E2h
0x1800423c3  lea     rax, [rsp+178h+var_124]
0x1800423c8  mov     [rsp+178h+var_48], rax
0x1800423d0  mov     [rsp+178h+var_40], rdx
0x1800423d8  lea     rax, [rsp+178h+var_120]
0x1800423dd  mov     [rsp+178h+var_58], rax
0x1800423e5  mov     [rsp+178h+var_50], rdx
0x1800423ed  lea     rax, [rsp+178h+var_11C]
0x1800423f2  mov     [rsp+178h+var_68], rax
0x1800423fa  mov     [rsp+178h+var_60], rdx
0x180042402  lea     rax, [rsp+178h+var_118]
0x180042407  mov     [rsp+178h+var_78], rax
0x18004240f  mov     [rsp+178h+var_70], rdx
0x180042417  lea     rax, [rsp+178h+var_110]
0x18004241c  mov     [rsp+178h+var_88], rax
0x180042424  mov     [rsp+178h+var_80], 8
0x180042430  lea     rax, [rsp+178h+var_114]
0x180042435  mov     [rsp+178h+var_98], rax
0x18004243d  mov     [rsp+178h+var_90], rdx
0x180042445  lea     rax, aSendupdatevirt; "SendUpdateVirtualDesktopPdu"
0x18004244c  mov     [rsp+178h+var_A8], rax
0x180042454  mov     [rsp+178h+var_A0], 1Ch
0x180042460  lea     rax, aRdpAvencIc3Cds_4; "Rdp::Avenc::Ic3::CDsGfxChannel::SendUpd"...
0x180042467  mov     [rsp+178h+var_B8], rax
0x18004246f  mov     [rsp+178h+var_B0], 3Ch ; '<'
0x18004247b  lea     rax, [rsp+178h+var_128]
0x180042480  mov     [rsp+178h+var_C8], rax
0x180042488  mov     [rsp+178h+var_C0], rdx
0x180042490  lea     rax, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180042497  mov     [rsp+178h+var_D8], rax
0x18004249f  mov     [rsp+178h+var_D0], 46h ; 'F'
0x1800424ab  lea     rax, [rsp+178h+var_F8]
0x1800424b3  mov     [rsp+178h+var_150], rax
0x1800424b8  mov     [rsp+178h+var_158], 0Ch
0x1800424c0  xor     r9d, r9d
0x1800424c3  xor     r8d, r8d
0x1800424c6  lea     rdx, word_1800AFFE2
0x1800424cd  lea     rcx, dword_1800C1058
0x1800424d4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800424d9  jmp     short loc_1800424E2
0x1800424db  mov     esi, [rsp+178h+arg_20]
0x1800424e2  mov     edi, 18h
0x1800424e7  mov     ecx, edi; unsigned __int64
0x1800424e9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800424ee  mov     r8, rax
0x1800424f1  mov     [rsp+178h+var_110], rax
0x1800424f6  mov     [rax], edi
0x1800424f8  mov     dword ptr [rax+4], 7
0x1800424ff  mov     [rax+8], r12d
0x180042503  mov     [rax+0Ch], r15d
0x180042507  mov     [rax+10h], r14d
0x18004250b  mov     [rax+14h], esi
0x18004250e  mov     rcx, [rbx]
0x180042511  mov     rax, [rcx+18h]
0x180042515  mov     [rsp+178h+var_140], r13
0x18004251a  mov     dword ptr [rsp+178h+var_148], 3
0x180042522  mov     dword ptr [rsp+178h+var_150], edi; char *
0x180042526  mov     [rsp+178h+var_158], 1
0x18004252e  lea     r9d, [rdi-16h]
0x180042532  mov     edx, edi
0x180042534  mov     rcx, rbx
0x180042537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004253c  mov     rcx, [rsp+178h]; this
0x180042544  lea     rdx, aFailedToSendRd_4; "Failed to send RDPDSGFX_PDU_CMDID_VIRTU"...
0x18004254b  mov     qword ptr [rsp+178h+var_158], rdx; int
0x180042550  mov     r9d, eax; char *
0x180042553  lea     r8, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004255a  mov     edx, 1F3h; void *
0x18004255f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180042564  nop
0x180042565  mov     rax, [rbx]
0x180042568  mov     rcx, rbx
0x18004256b  mov     rax, [rax+10h]
0x18004256f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042574  nop
0x180042575  xor     eax, eax
0x180042577  jmp     short loc_18004257D
0x180042579  mov     eax, [rsp+178h+var_128]
0x18004257d  mov     rcx, [rsp+178h+var_38]
0x180042585  xor     rcx, rsp; StackCookie
0x180042588  call    __security_check_cookie
0x18004258d  lea     r11, [rsp+178h+var_28]
0x180042595  mov     rbx, [r11+38h]
0x180042599  mov     rsi, [r11+40h]
0x18004259d  mov     rsp, r11
0x1800425a0  pop     r15
0x1800425a2  pop     r14
0x1800425a4  pop     r13
0x1800425a6  pop     r12
0x1800425a8  pop     rdi
0x1800425a9  retn
```
