# WindowsPerformanceRecorder::CETWProperties::CreateSystemRundownSession(bool,ushort const *,ushort const *,ushort const *,ulong *,unsigned __int64,bool,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)

- ea: `0x180024074`
- end: `0x180024269`
- name: `?CreateSystemRundownSession@CETWProperties@WindowsPerformanceRecorder@@SAJ_NPEBG11PEAK_K0PEAPEAUCEventSession@12@@Z`
- size: `501`
- prototype: `__int64 __fastcall(char, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int64, bool, struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800236b0`

## callees

- `0x18000b34c`
- `0x18000b5a0`
- `0x18000b9e0`
- `0x18000bca0`
- `0x180013f6c`
- `0x18001e6e0`
- `0x180024074`
- `0x18004794c`
- `0x18004ece0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800241d3`

## string_xrefs

- `0x180024110`: `COMGUARD`
- `0x18002417d`: `COMGUARD`
- `0x180024125`: `CreateSystemRundownSession`
- `0x180024192`: `CreateSystemRundownSession`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::CreateSystemRundownSession(
        char a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int64 a6,
        bool a7,
        struct WindowsPerformanceRecorder::CETWProperties::CEventSession **a8)
{
  unsigned __int64 v11; // r9
  signed int ETWSession; // eax
  unsigned int v13; // esi
  __int64; // rax
  unsigned int *v15; // r10
  signed int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v19; // rbx
  char *v20; // [rsp+28h] [rbp-170h]
  _BYTE v21[16]; // [rsp+50h] [rbp-148h] BYREF
  unsigned __int64 v22; // [rsp+60h] [rbp-138h]

  if ( a6 )
    v11 = 4 * a6 + 4;
  else
    v11 = 0;
  ETWSession = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int64, struct WindowsPerformanceRecorder::CETWProperties::CEventSession **, const unsigned __int16 *, bool, _QWORD, __int64))WindowsPerformanceRecorder::CETWProperties::CreateETWSession)(
                 a2,
                 a3,
                 2,
                 v11,
                 a8,
                 a4,
                 a7,
                 0,
                 -2);
  v13 = ETWSession;
  if ( ETWSession < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (const char *)(unsigned __int8)"CreateSystemRundownSession",
      (const char *)0x403,
      ETWSession,
      "COMGUARD",
      v20);
     = v13;
    goto LABEL_27;
  }
  *(_DWORD *)*a8 = 4;
  v15 = (unsigned int *)*((_QWORD *)*a8 + 1);
  if ( a6 )
  {
    v16 = WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(
            (struct _TRACE_ENABLE_FLAG_EXT_HEADER *)((char *)v15 + *((unsigned __int16 *)v15 + 36)),
            (unsigned __int64)v15 + *v15,
            3u,
            a5,
            4 * (unsigned __int16)a6);
    v17 = v16;
    if ( v16 < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (const char *)(unsigned __int8)"CreateSystemRundownSession",
        (const char *)0x410,
        v16,
        "COMGUARD",
        v20);
       = v17;
      goto LABEL_27;
    }
  }
  else
  {
    v15[18] = 0;
  }
  if ( a1 )
  {
    WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
      (WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v21,
      &KernelRundownGuid);
    v18 = _o__wcsicmp(a2, L"Circular Kernel Context Logger");
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v22 = (-(__int64)(v18 != 0) & 0xFFFFFFFFFFFFFFFAuLL) + 8;
      v19 = *a8;
      if ( *((_QWORD *)*a8 + 4) == *((_QWORD *)*a8 + 5) )
      {
        std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventProvider const &>(
          (char *)v19 + 24,
          *((_QWORD *)*a8 + 4),
          v21);
      }
      else
      {
        WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
          *((WindowsPerformanceRecorder::CETWProperties::CEventProvider **)*a8 + 4),
          (const struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v21);
        *((_QWORD *)v19 + 4) += 264LL;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_180024255);
LABEL_17:
        WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v21);
         = 2147942414LL;
LABEL_27:
        ;
      }
      if ( __eh34_catch_type(0, std::length_error `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, std::length_error `RTTI Type Descriptor', &loc_180024266);
        goto LABEL_17;
      }
    }
    WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v21);
  }
   = 0;
  goto LABEL_27;
}

```

## disassembly

```asm
0x180024074  mov     rax, rsp
0x180024077  push    rsi
0x180024078  push    rdi
0x180024079  push    r12
0x18002407b  push    r14
0x18002407d  push    r15
0x18002407f  sub     rsp, 170h
0x180024086  mov     [rsp+198h+var_158], 0FFFFFFFFFFFFFFFEh
0x18002408f  mov     [rax+8], rbx
0x180024093  mov     rax, cs:__security_cookie
0x18002409a  xor     rax, rsp
0x18002409d  mov     [rsp+198h+var_38], rax
0x1800240a5  mov     r11, r9
0x1800240a8  mov     r10, r8
0x1800240ab  mov     r14, rdx
0x1800240ae  mov     r15b, cl
0x1800240b1  mov     r12, [rsp+198h+arg_20]
0x1800240b9  mov     rdi, [rsp+198h+arg_38]
0x1800240c1  mov     rbx, [rsp+198h+arg_28]
0x1800240c9  test    rbx, rbx
0x1800240cc  jz      short loc_1800240D8
0x1800240ce  lea     r9, ds:4[rbx*4]
0x1800240d6  jmp     short loc_1800240DB
0x1800240d8  xor     r9d, r9d
0x1800240db  mov     [rsp+198h+var_160], 0
0x1800240e4  mov     al, [rsp+198h+arg_30]
0x1800240eb  mov     [rsp+198h+var_168], al
0x1800240ef  mov     [rsp+198h+var_170], r11; char *
0x1800240f4  mov     [rsp+198h+Format], rdi
0x1800240f9  mov     r8d, 2
0x1800240ff  mov     rdx, r10
0x180024102  mov     rcx, r14
0x180024105  call    ?CreateETWSession@CETWProperties@WindowsPerformanceRecorder@@CAJPEBG0W4__MIDL_IProfile_0001@@_KPEAPEAUCEventSession@12@0_N0@Z; WindowsPerformanceRecorder::CETWProperties::CreateETWSession(ushort const *,ushort const *,__MIDL_IProfile_0001,unsigned __int64,WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ushort const *,bool,ushort const *)
0x18002410a  mov     esi, eax
0x18002410c  test    eax, eax
0x18002410e  jns     short loc_18002413D
0x180024110  lea     rdx, aComguard; "COMGUARD"
0x180024117  mov     [rsp+198h+Format], rdx; Format
0x18002411c  mov     r9d, eax; unsigned int
0x18002411f  mov     r8d, 403h; char *
0x180024125  lea     rdx, aCreatesystemru; "CreateSystemRundownSession"
0x18002412c  mov     ecx, 2; this
0x180024131  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180024136  mov     eax, esi
0x180024138  jmp     loc_18002422D
0x18002413d  mov     rax, [rdi]
0x180024140  mov     dword ptr [rax], 4
0x180024146  mov     rax, [rdi]
0x180024149  mov     r10, [rax+8]
0x18002414d  test    rbx, rbx
0x180024150  jz      short loc_1800241AA
0x180024152  shl     bx, 2
0x180024156  mov     r8d, 3; unsigned __int16
0x18002415c  mov     edx, [r10]
0x18002415f  add     rdx, r10; void *
0x180024162  movzx   ecx, word ptr [r10+48h]
0x180024167  add     rcx, r10; struct _TRACE_ENABLE_FLAG_EXT_HEADER *
0x18002416a  mov     word ptr [rsp+198h+Format], bx; unsigned __int16
0x18002416f  mov     r9, r12; void *
0x180024172  call    ?AddExtendedFlagEntry@CETWProperties@WindowsPerformanceRecorder@@CAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXG1G@Z; WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,ushort,void const *,ushort)
0x180024177  mov     ebx, eax
0x180024179  test    eax, eax
0x18002417b  jns     short loc_1800241B2
0x18002417d  lea     rdx, aComguard; "COMGUARD"
0x180024184  mov     [rsp+198h+Format], rdx; Format
0x180024189  mov     r9d, eax; unsigned int
0x18002418c  mov     r8d, 410h; char *
0x180024192  lea     rdx, aCreatesystemru; "CreateSystemRundownSession"
0x180024199  mov     ecx, 2; this
0x18002419e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800241a3  mov     eax, ebx
0x1800241a5  jmp     loc_18002422D
0x1800241aa  mov     dword ptr [r10+48h], 0
0x1800241b2  test    r15b, r15b
0x1800241b5  jz      short loc_18002422B
0x1800241b7  lea     rdx, KernelRundownGuid; struct _GUID *
0x1800241be  lea     rcx, [rsp+198h+var_148]; this
0x1800241c3  call    ??0CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@AEBU_GUID@@@Z; WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(_GUID const &)
0x1800241c8  nop
0x1800241c9  lea     rdx, aCircularKernel; "Circular Kernel Context Logger"
0x1800241d0  mov     rcx, r14
0x1800241d3  call    cs:__imp__o__wcsicmp
0x1800241d9  neg     eax
0x1800241db  sbb     rcx, rcx
0x1800241de  and     rcx, 0FFFFFFFFFFFFFFFAh
0x1800241e2  add     rcx, 8
0x1800241e6  mov     [rsp+198h+var_138], rcx
0x1800241eb  mov     rbx, [rdi]
0x1800241ee  mov     rax, [rbx+20h]
0x1800241f2  cmp     rax, [rbx+28h]
0x1800241f6  jz      short loc_18002420F
0x1800241f8  lea     rdx, [rsp+198h+var_148]; struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *
0x1800241fd  mov     rcx, rax; this
0x180024200  call    ??0CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@AEBU012@@Z; WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(WindowsPerformanceRecorder::CETWProperties::CEventProvider const &)
0x180024205  add     qword ptr [rbx+20h], 108h
0x18002420d  jmp     short loc_180024221
0x18002420f  lea     r8, [rsp+198h+var_148]
0x180024214  mov     rdx, rax
0x180024217  lea     rcx, [rbx+18h]
0x18002421b  call    ??$_Emplace_reallocate@AEBUCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@?$vector@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAUCEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAU234@AEBU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventProvider const &>(WindowsPerformanceRecorder::CETWProperties::CEventProvider * const,WindowsPerformanceRecorder::CETWProperties::CEventProvider const &)
0x180024220  nop
0x180024221  lea     rcx, [rsp+198h+var_148]; this
0x180024226  call    ??1CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider(void)
0x18002422b  xor     eax, eax
0x18002422d  mov     rcx, [rsp+198h+var_38]
0x180024235  xor     rcx, rsp; StackCookie
0x180024238  call    __security_check_cookie
0x18002423d  mov     rbx, [rsp+198h+arg_0]
0x180024245  add     rsp, 170h
0x18002424c  pop     r15
0x18002424e  pop     r14
0x180024250  pop     r12
0x180024252  pop     rdi
0x180024253  pop     rsi
0x180024254  retn
0x180024255  lea     rcx, [rsp+198h+var_148]; this
0x18002425a  call    ??1CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider(void)
0x18002425f  mov     eax, 8007000Eh
0x180024264  jmp     short loc_18002422D
0x180024266  jmp     short loc_180024255
```
