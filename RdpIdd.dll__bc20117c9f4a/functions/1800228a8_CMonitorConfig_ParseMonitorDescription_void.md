# CMonitorConfig::ParseMonitorDescription(void)

- ea: `0x1800228a8`
- end: `0x180022988`
- name: `?ParseMonitorDescription@CMonitorConfig@@AEAAXXZ`
- size: `224`
- prototype: `void __fastcall(CMonitorConfig *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021f78`

## callees

- `0x1800089f0`
- `0x1800106b8`
- `0x18001ddbc`
- `0x1800228a8`
- `0x180036d68`
- `0x180039334`
- `0x1800398f0`

## string_xrefs

- `0x180022942`: `onecoreuap\termsrv\rdp_bin\win\rdpidd\monitorconfig.cpp`
- `0x180022967`: `onecoreuap\termsrv\rdp_bin\win\rdpidd\monitorconfig.cpp`

## pseudocode

```c
void __fastcall CMonitorConfig::ParseMonitorDescription(CMonitorConfig *this)
{
  int v1; // eax
  unsigned int ColorDepths; // eax
  const void *v4; // rdx
  int v5; // r8d
  unsigned int ColorimetryData; // eax
  unsigned int v7; // eax
  const char *v8; // [rsp+28h] [rbp-30h]
  _OWORD v9[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v11; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 76);
  if ( v1 == 1 )
  {
    ColorDepths = EDID_V1_GetColorDepths(
                    *((_DWORD *)this + 72) - (unsigned int)*((_QWORD *)this + 35),
                    *((const unsigned __int8 **)this + 35),
                    (CMonitorConfig *)((char *)this + 4));
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
      (const char *)ColorDepths,
      (int)"Failed to get color depths from Edid",
      v8);
  }
  else
  {
    if ( v1 != 2 )
    {
      v7 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
        (const char *)v7,
        (int)"Unsupported monitor description type specified",
        v8);
    }
    v4 = (const void *)*((_QWORD *)this + 35);
    v5 = *((_DWORD *)this + 72);
    memset(v9, 0, sizeof(v9));
    DisplayID_Initialize((struct DisplayIDObj *)v9, v4, v5 - (_DWORD)v4);
    v11 = 0;
    ColorimetryData = DisplayID_GetColorimetryData(
                        (const struct DisplayIDObj *)v9,
                        (struct DISPLAYID_COLORIMETRY_DATA *)&v11,
                        (CMonitorConfig *)((char *)this + 4));
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp",
      (const char *)ColorimetryData,
      (int)"Failed to get color depths from DisplayId",
      v8);
  }
}

```

## disassembly

```asm
0x1800228a8  push    rbx
0x1800228aa  sub     rsp, 50h
0x1800228ae  mov     eax, [rcx+130h]
0x1800228b4  mov     rbx, rcx
0x1800228b7  cmp     eax, 1
0x1800228ba  jnz     short loc_1800228E7
0x1800228bc  mov     rdx, [rcx+118h]; unsigned __int8 *
0x1800228c3  lea     r8, [rcx+4]; struct DISPLAY_COLOR_DEPTHS *
0x1800228c7  mov     ecx, [rcx+120h]
0x1800228cd  sub     ecx, edx; unsigned int
0x1800228cf  call    ?EDID_V1_GetColorDepths@@YAJKPEBEPEAUDISPLAY_COLOR_DEPTHS@@@Z; EDID_V1_GetColorDepths(ulong,uchar const *,DISPLAY_COLOR_DEPTHS *)
0x1800228d4  lea     rdx, aFailedToGetCol_0; "Failed to get color depths from Edid"
0x1800228db  mov     qword ptr [rsp+58h+var_38], rdx
0x1800228e0  mov     edx, 194h
0x1800228e5  jmp     short loc_18002293D
0x1800228e7  cmp     eax, 2
0x1800228ea  jnz     short loc_180022958
0x1800228ec  mov     rdx, [rcx+118h]; void *
0x1800228f3  xorps   xmm0, xmm0
0x1800228f6  mov     r8d, [rcx+120h]
0x1800228fd  lea     rcx, [rsp+58h+var_28]; struct DisplayIDObj *
0x180022902  sub     r8d, edx; unsigned int
0x180022905  movups  [rsp+58h+var_28], xmm0
0x18002290a  movups  [rsp+58h+var_18], xmm0
0x18002290f  call    ?DisplayID_Initialize@@YAXPEAUDisplayIDObj@@PEBXI@Z; DisplayID_Initialize(DisplayIDObj *,void const *,uint)
0x180022914  lea     r8, [rbx+4]; struct DISPLAY_COLOR_DEPTHS *
0x180022918  mov     [rsp+58h+arg_0], 0
0x18002291d  lea     rdx, [rsp+58h+arg_0]; struct DISPLAYID_COLORIMETRY_DATA *
0x180022922  lea     rcx, [rsp+58h+var_28]; struct DisplayIDObj *
0x180022927  call    ?DisplayID_GetColorimetryData@@YAJPEBUDisplayIDObj@@PEAUDISPLAYID_COLORIMETRY_DATA@@PEAUDISPLAY_COLOR_DEPTHS@@@Z; DisplayID_GetColorimetryData(DisplayIDObj const *,DISPLAYID_COLORIMETRY_DATA *,DISPLAY_COLOR_DEPTHS *)
0x18002292c  lea     rdx, aFailedToGetCol; "Failed to get color depths from Display"...
0x180022933  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180022938  mov     edx, 1A6h; void *
0x18002293d  mov     rcx, [rsp+58h]; this
0x180022942  lea     r8, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180022949  mov     r9d, eax; char *
0x18002294c  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022951  add     rsp, 50h
0x180022955  pop     rbx
0x180022956  retn
0x180022958  mov     ecx, 80070057h
0x18002295d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180022962  mov     rcx, [rsp+58h]; this
0x180022967  lea     r8, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002296e  mov     r9d, eax; char *
0x180022971  mov     edx, 1AAh; void *
0x180022976  lea     rax, aUnsupportedMon_0; "Unsupported monitor description type sp"...
0x18002297d  mov     qword ptr [rsp+58h+var_38], rax; int
0x180022982  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
