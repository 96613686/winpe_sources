# Rdp::Avenc::CProcessorBase<Rdp::Avenc::SinkWriter::CMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::FindMonitor(_GUID const &)

- ea: `0x180033190`
- end: `0x1800333aa`
- name: `?FindMonitor@?$CProcessorBase@VCMonitorContext@SinkWriter@Avenc@Rdp@@UIFileIoControlEvents1@34@UIFileIoChannelEvents@34@UISerializePropertyBag@34@@Avenc@Rdp@@QEAA?AV?$com_ptr_t@VCMonitorContext@SinkWriter@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBU_GUID@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180033ba4`

## callees

- `0x1800080cc`
- `0x18000f5bc`
- `0x1800153f8`
- `0x1800199cc`
- `0x180033190`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800331c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800331c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033262`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033262`

## string_xrefs

- `0x1800332f6`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180033398`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x1800332fd`: `Rdp::Avenc::CProcessorBase<class Rdp::Avenc::SinkWriter::CMonitorContext,struct Rdp::Avenc::IFileIoControlEvents1,struct Rdp::Avenc::IFileIoChannelEvents,struct Rdp::Avenc::ISerializePropertyBag>::FindMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::SinkWriter::CMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::FindMonitor(
        RTL_SRWLOCK *a1,
        _QWORD *a2,
        _DWORD *a3)
{
  RTL_SRWLOCK *v6; // r15
  char v7; // si
  char *Ptr; // rbp
  char *v9; // rdi
  char *v10; // rbx
  char v11; // cl
  char **v12; // rax
  __int64 v13; // rcx
  int v15; // ebx
  int v16; // edi
  int v17; // esi
  int v18; // ebp
  int v19; // r14d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  int v24; // r10d
  int v25; // r11d
  int v26; // ebx
  int v27; // edi
  int v28; // esi
  int v29; // ebp
  int v30; // r14d
  int v31; // r15d
  int v32; // r12d
  unsigned int v33; // eax
  int v34; // edx
  int v35; // r10d
  int v36; // r11d
  char *v37; // [rsp+28h] [rbp-D0h]
  __int64 v38; // [rsp+30h] [rbp-C8h]
  __int64 v39; // [rsp+38h] [rbp-C0h]
  __int64 v40; // [rsp+40h] [rbp-B8h]
  __int64 v41; // [rsp+48h] [rbp-B0h]
  __int64 v42; // [rsp+50h] [rbp-A8h]
  __int64 v43; // [rsp+58h] [rbp-A0h]
  __int64 v44; // [rsp+60h] [rbp-98h]
  __int64 v45; // [rsp+68h] [rbp-90h]
  __int64 v46; // [rsp+70h] [rbp-88h]
  __int64 v47; // [rsp+78h] [rbp-80h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v6 = a1 + 18;
  v7 = 1;
  AcquireSRWLockShared(a1 + 18);
  Ptr = (char *)a1[16].Ptr;
  v9 = (char *)*((_QWORD *)Ptr + 1);
  v10 = Ptr;
  while ( !v9[25] )
  {
    if ( memcmp_0(v9 + 32, a3, 0x10u) >= 0 )
    {
      v11 = 0;
      v10 = v9;
    }
    else
    {
      v11 = 1;
    }
    v12 = (char **)(v9 + 16);
    if ( !v11 )
      v12 = (char **)v9;
    v9 = *v12;
  }
  if ( v10[25] || memcmp_0(a3, v10 + 32, 0x10u) < 0 )
    v7 = 0;
  if ( !v7 )
    v10 = Ptr;
  if ( v10 == Ptr )
  {
    v15 = *((unsigned __int8 *)a3 + 10);
    v16 = *((unsigned __int8 *)a3 + 9);
    v17 = *((unsigned __int8 *)a3 + 8);
    v18 = *((unsigned __int16 *)a3 + 3);
    v19 = *((unsigned __int16 *)a3 + 2);
    Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      Ifr,
      (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
      "Rdp::Avenc::CProcessorBase<class Rdp::Avenc::SinkWriter::CMonitorContext,struct Rdp::Avenc::IFileIoControlEvents1,"
      "struct Rdp::Avenc::IFileIoChannelEvents,struct Rdp::Avenc::ISerializePropertyBag>::FindMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      0x143u,
      *a3,
      v19,
      v18,
      v17,
      v16,
      v15,
      v25,
      v24,
      v23,
      v22,
      v21);
    v26 = *((unsigned __int8 *)a3 + 12);
    v27 = *((unsigned __int8 *)a3 + 11);
    v28 = *((unsigned __int8 *)a3 + 10);
    v29 = *((unsigned __int8 *)a3 + 9);
    v30 = *((unsigned __int8 *)a3 + 8);
    v31 = *((unsigned __int16 *)a3 + 3);
    v32 = *((unsigned __int16 *)a3 + 2);
    v33 = wil::verify_hresult<long>(2147943568LL);
    LODWORD(v47) = v34;
    LODWORD(v46) = v35;
    LODWORD(v45) = v36;
    LODWORD(v44) = v26;
    LODWORD(v43) = v27;
    LODWORD(v42) = v28;
    LODWORD(v41) = v29;
    LODWORD(v40) = v30;
    LODWORD(v39) = v31;
    LODWORD(v38) = v32;
    LODWORD(v37) = *a3;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v33,
      (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
      v37,
      v38,
      v39,
      v40,
      v41,
      v42,
      v43,
      v44,
      v45,
      v46,
      v47);
  }
  v13 = *((_QWORD *)v10 + 6);
  *a2 = v13;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  ReleaseSRWLockShared(v6);
  return a2;
}

```

## disassembly

```asm
0x180033190  mov     rax, rsp
0x180033193  push    rbx
0x180033194  push    rbp
0x180033195  push    rsi
0x180033196  push    rdi
0x180033197  push    r12
0x180033199  push    r13
0x18003319b  push    r14
0x18003319d  push    r15
0x18003319f  sub     rsp, 0B8h
0x1800331a6  mov     r13, r8
0x1800331a9  mov     r14, rdx
0x1800331ac  mov     rbx, rcx
0x1800331af  xor     r12d, r12d
0x1800331b2  lea     r15, [rcx+90h]
0x1800331b9  mov     [rax-70h], r15
0x1800331bd  mov     sil, 1
0x1800331c0  mov     [rax-68h], sil
0x1800331c4  mov     rcx, r15; SRWLock
0x1800331c7  call    cs:__imp_AcquireSRWLockShared
0x1800331cd  nop
0x1800331ce  mov     rbp, [rbx+80h]
0x1800331d5  mov     rdi, [rbp+8]
0x1800331d9  xor     eax, eax
0x1800331db  mov     [rsp+0F8h+var_54], eax
0x1800331e2  mov     rbx, rbp
0x1800331e5  jmp     short loc_180033215
0x1800331e7  lea     rcx, [rdi+20h]; Buf1
0x1800331eb  mov     r8d, 10h; Size
0x1800331f1  mov     rdx, r13; Buf2
0x1800331f4  call    memcmp_0
0x1800331f9  test    eax, eax
0x1800331fb  jns     short loc_180033202
0x1800331fd  mov     cl, sil
0x180033200  jmp     short loc_180033208
0x180033202  mov     cl, r12b
0x180033205  mov     rbx, rdi
0x180033208  lea     rax, [rdi+10h]
0x18003320c  test    cl, cl
0x18003320e  cmovz   rax, rdi
0x180033212  mov     rdi, [rax]
0x180033215  cmp     [rdi+19h], r12b
0x180033219  jz      short loc_1800331E7
0x18003321b  cmp     [rbx+19h], r12b
0x18003321f  jnz     short loc_180033237
0x180033221  lea     rdx, [rbx+20h]; Buf2
0x180033225  mov     r8d, 10h; Size
0x18003322b  mov     rcx, r13; Buf1
0x18003322e  call    memcmp_0
0x180033233  test    eax, eax
0x180033235  jns     short loc_18003323A
0x180033237  mov     sil, r12b
0x18003323a  test    sil, sil
0x18003323d  cmovz   rbx, rbp
0x180033241  cmp     rbx, rbp
0x180033244  jz      short loc_18003327F
0x180033246  mov     rcx, [rbx+30h]
0x18003324a  mov     [r14], rcx
0x18003324d  test    rcx, rcx
0x180033250  jz      short loc_18003325F
0x180033252  mov     rax, [rcx]
0x180033255  mov     rax, [rax+8]
0x180033259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003325e  nop
0x18003325f  mov     rcx, r15; SRWLock
0x180033262  call    cs:__imp_ReleaseSRWLockShared
0x180033268  mov     rax, r14
0x18003326b  add     rsp, 0B8h
0x180033272  pop     r15
0x180033274  pop     r14
0x180033276  pop     r13
0x180033278  pop     r12
0x18003327a  pop     rdi
0x18003327b  pop     rsi
0x18003327c  pop     rbp
0x18003327d  pop     rbx
0x18003327e  retn
0x18003327f  movzx   edx, byte ptr [r13+0Fh]
0x180033284  movzx   r8d, byte ptr [r13+0Eh]
0x180033289  movzx   r9d, byte ptr [r13+0Dh]
0x18003328e  movzx   r10d, byte ptr [r13+0Ch]
0x180033293  movzx   r11d, byte ptr [r13+0Bh]
0x180033298  movzx   ebx, byte ptr [r13+0Ah]
0x18003329d  movzx   edi, byte ptr [r13+9]
0x1800332a2  movzx   esi, byte ptr [r13+8]
0x1800332a7  movzx   ebp, word ptr [r13+6]
0x1800332ac  movzx   r14d, word ptr [r13+4]
0x1800332b1  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x1800332b6  mov     rcx, rax; this
0x1800332b9  mov     dword ptr [rsp+0F8h+var_80], edx
0x1800332bd  mov     dword ptr [rsp+0F8h+var_88], r8d
0x1800332c2  mov     dword ptr [rsp+0F8h+var_90], r9d
0x1800332c7  mov     dword ptr [rsp+0F8h+var_98], r10d
0x1800332cc  mov     dword ptr [rsp+0F8h+var_A0], r11d
0x1800332d1  mov     dword ptr [rsp+0F8h+var_A8], ebx
0x1800332d5  mov     dword ptr [rsp+0F8h+var_B0], edi
0x1800332d9  mov     dword ptr [rsp+0F8h+var_B8], esi
0x1800332dd  mov     dword ptr [rsp+0F8h+var_C0], ebp
0x1800332e1  mov     dword ptr [rsp+0F8h+var_C8], r14d
0x1800332e6  mov     eax, [r13+0]
0x1800332ea  mov     dword ptr [rsp+0F8h+var_D0], eax
0x1800332ee  mov     [rsp+0F8h+var_D8], 143h; unsigned int
0x1800332f6  lea     r9, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800332fd  lea     r8, aRdpAvencCproce_2; "Rdp::Avenc::CProcessorBase<class Rdp::A"...
0x180033304  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x18003330b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180033310  movzx   edx, byte ptr [r13+0Fh]
0x180033315  movzx   r10d, byte ptr [r13+0Eh]
0x18003331a  movzx   r11d, byte ptr [r13+0Dh]
0x18003331f  movzx   ebx, byte ptr [r13+0Ch]
0x180033324  movzx   edi, byte ptr [r13+0Bh]
0x180033329  movzx   esi, byte ptr [r13+0Ah]
0x18003332e  movzx   ebp, byte ptr [r13+9]
0x180033333  movzx   r14d, byte ptr [r13+8]
0x180033338  movzx   r15d, word ptr [r13+6]
0x18003333d  movzx   r12d, word ptr [r13+4]
0x180033342  mov     ecx, 80070490h
0x180033347  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003334c  mov     r9d, eax; char *
0x18003334f  mov     rcx, [rsp+0F8h]; this
0x180033357  mov     dword ptr [rsp+0F8h+var_80], edx
0x18003335b  mov     dword ptr [rsp+0F8h+var_88], r10d
0x180033360  mov     dword ptr [rsp+0F8h+var_90], r11d
0x180033365  mov     dword ptr [rsp+0F8h+var_98], ebx
0x180033369  mov     dword ptr [rsp+0F8h+var_A0], edi
0x18003336d  mov     dword ptr [rsp+0F8h+var_A8], esi
0x180033371  mov     dword ptr [rsp+0F8h+var_B0], ebp
0x180033375  mov     dword ptr [rsp+0F8h+var_B8], r14d
0x18003337a  mov     dword ptr [rsp+0F8h+var_C0], r15d
0x18003337f  mov     dword ptr [rsp+0F8h+var_C8], r12d
0x180033384  mov     eax, [r13+0]
0x180033388  mov     dword ptr [rsp+0F8h+var_D0], eax; char *
0x18003338c  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x180033393  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180033398  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003339f  mov     edx, 148h; void *
0x1800333a4  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
