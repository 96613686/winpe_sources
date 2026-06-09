# Rdp::Avenc::Ic3::CDsGfxChannel::OnDataReceived(ulong,uchar *)

- ea: `0x1800411f0`
- end: `0x1800413a2`
- name: `?OnDataReceived@CDsGfxChannel@Ic3@Avenc@Rdp@@UEAAJKPEAE@Z`
- size: `434`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CDsGfxChannel *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800146bc`
- `0x180015480`
- `0x1800411f0`
- `0x1800414a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004125d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004134d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004125d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004134d`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CDsGfxChannel::OnDataReceived(
        Rdp::Avenc::Ic3::CDsGfxChannel *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  char v6; // bl
  bool v7; // si
  bool v8; // r14
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  const char *v12; // r9
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+28h] [rbp-50h]
  char *v22; // [rsp+30h] [rbp-48h]
  char *v23; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v20,
      10,
      &WPP_6e229f5587833f8d50cdea4c7857a278_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v18) = a2 < 0x10;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
      (const char *)0x8007007ALL,
      v18,
      (bool)"Buffer size is too small to cast to RDPDSGFX_PDU_HEADER",
      v22);
    if ( *((_DWORD *)a3 + 3) == 1 )
    {
      LOBYTE(v19) = *((_DWORD *)a3 + 2) < 8u;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
        (const char *)0x8007007ALL,
        v19,
        (bool)"Buffer size is too small to cast to RDPDSGFX_CAPS_ADVERTISE_PDU",
        v23);
      Rdp::Avenc::Ic3::CDsGfxChannel::ProcessCapsAdvertise(
        (Rdp::Avenc::Ic3::CDsGfxChannel *)((char *)this - 80),
        *((_DWORD *)a3 + 2) - 8,
        a3 + 16);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = GetCurrentThreadId();
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        v21,
        11,
        &WPP_6e229f5587833f8d50cdea4c7857a278_Traceguids,
        v14);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC3,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800411f0  mov     [rsp+arg_0], rbx
0x1800411f5  mov     [rsp+arg_10], rsi
0x1800411fa  push    rdi
0x1800411fb  push    r12
0x1800411fd  push    r13
0x1800411ff  push    r14
0x180041201  push    r15
0x180041203  sub     rsp, 50h
0x180041207  mov     rdi, r8
0x18004120a  mov     r12d, edx
0x18004120d  mov     r13, rcx
0x180041210  lea     rcx, WPP_GLOBAL_Control
0x180041217  mov     rax, cs:WPP_GLOBAL_Control
0x18004121e  mov     bl, 1
0x180041220  cmp     rax, rcx
0x180041223  jz      short loc_180041235
0x180041225  test    [rax+1Ch], bl
0x180041228  jz      short loc_180041235
0x18004122a  cmp     byte ptr [rax+19h], 4
0x18004122e  jb      short loc_180041235
0x180041230  mov     sil, bl
0x180041233  jmp     short loc_180041238
0x180041235  xor     sil, sil
0x180041238  lea     rax, WPP_RECORDER_INITIALIZED
0x18004123f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180041246  setnz   r14b
0x18004124a  test    sil, sil
0x18004124d  jnz     short loc_18004125D
0x18004124f  test    r14b, r14b
0x180041252  jnz     short loc_18004125D
0x180041254  lea     r15, WPP_6e229f5587833f8d50cdea4c7857a278_Traceguids
0x18004125b  jmp     short loc_180041294
0x18004125d  call    cs:__imp_GetCurrentThreadId
0x180041263  mov     dword ptr [rsp+78h+var_38], eax; char
0x180041267  lea     r15, WPP_6e229f5587833f8d50cdea4c7857a278_Traceguids
0x18004126e  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180041273  mov     word ptr [rsp+78h+var_48], 0Ah; char *
0x18004127a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041281  mov     r9, [rcx+28h]; int
0x180041285  mov     r8b, r14b; int
0x180041288  mov     dl, sil; int
0x18004128b  mov     rcx, [rcx+10h]; int
0x18004128f  call    WPP_RECORDER_AND_TRACE_SF_D
0x180041294  cmp     r12d, 10h
0x180041298  setb    al
0x18004129b  mov     rcx, [rsp+78h]; this
0x1800412a0  lea     rdx, aBufferSizeIsTo_7; "Buffer size is too small to cast to RDP"...
0x1800412a7  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x1800412ac  mov     byte ptr [rsp+78h+var_58], al; int
0x1800412b0  mov     esi, 8007007Ah
0x1800412b5  mov     r9d, esi; char *
0x1800412b8  lea     r8, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800412bf  mov     edx, 0ABh; void *
0x1800412c4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800412c9  cmp     dword ptr [rdi+0Ch], 1
0x1800412cd  jnz     short loc_180041312
0x1800412cf  cmp     dword ptr [rdi+8], 8
0x1800412d3  setb    al
0x1800412d6  mov     rcx, [rsp+78h]; this
0x1800412db  lea     rdx, aBufferSizeIsTo_2; "Buffer size is too small to cast to RDP"...
0x1800412e2  mov     qword ptr [rsp+78h+var_50], rdx; int
0x1800412e7  mov     byte ptr [rsp+78h+var_58], al; int
0x1800412eb  mov     r9d, esi; char *
0x1800412ee  lea     r8, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800412f5  mov     edx, 0B6h; void *
0x1800412fa  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800412ff  lea     r8, [rdi+10h]; void *
0x180041303  mov     edx, [rdi+8]
0x180041306  sub     edx, 8; unsigned int
0x180041309  lea     rcx, [r13-50h]; this
0x18004130d  call    ?ProcessCapsAdvertise@CDsGfxChannel@Ic3@Avenc@Rdp@@AEAAXIPEBX@Z; Rdp::Avenc::Ic3::CDsGfxChannel::ProcessCapsAdvertise(uint,void const *)
0x180041312  mov     rax, cs:WPP_GLOBAL_Control
0x180041319  lea     rcx, WPP_GLOBAL_Control
0x180041320  cmp     rax, rcx
0x180041323  jz      short loc_180041330
0x180041325  test    [rax+1Ch], bl
0x180041328  jz      short loc_180041330
0x18004132a  cmp     byte ptr [rax+19h], 4
0x18004132e  jnb     short loc_180041332
0x180041330  xor     bl, bl
0x180041332  lea     rax, WPP_RECORDER_INITIALIZED
0x180041339  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180041340  setnz   dil
0x180041344  test    bl, bl
0x180041346  jnz     short loc_18004134D
0x180041348  test    dil, dil
0x18004134b  jz      short loc_18004137C
0x18004134d  call    cs:__imp_GetCurrentThreadId
0x180041353  mov     dword ptr [rsp+78h+var_38], eax; char
0x180041357  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18004135c  mov     word ptr [rsp+78h+var_48], 0Bh; __int16
0x180041363  mov     rcx, cs:WPP_GLOBAL_Control
0x18004136a  mov     r9, [rcx+28h]; int
0x18004136e  mov     r8b, dil; int
0x180041371  mov     dl, bl; int
0x180041373  mov     rcx, [rcx+10h]; int
0x180041377  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004137c  xor     eax, eax
0x18004137e  jmp     short loc_180041387
0x180041380  mov     eax, [rsp+78h+arg_8]
0x180041387  lea     r11, [rsp+78h+var_28]
0x18004138c  mov     rbx, [r11+30h]
0x180041390  mov     rsi, [r11+40h]
0x180041394  mov     rsp, r11
0x180041397  pop     r15
0x180041399  pop     r14
0x18004139b  pop     r13
0x18004139d  pop     r12
0x18004139f  pop     rdi
0x1800413a0  retn
```
