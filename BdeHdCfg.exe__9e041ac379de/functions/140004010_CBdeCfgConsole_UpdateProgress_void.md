# CBdeCfgConsole::UpdateProgress(void)

- ea: `0x140004010`
- end: `0x1400041f8`
- name: `?UpdateProgress@CBdeCfgConsole@@AEAAJXZ`
- size: `488`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140003520`

## callees

- `0x140001008`
- `0x140002480`
- `0x14000343c`
- `0x140004010`
- `0x140004460`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000417e`
- `KERNEL32!FormatMessageW` at `0x14000417e`
- `KERNEL32!GetLastError` at `0x140004188`
- `KERNEL32!GetLastError` at `0x140004188`
- `KERNEL32!LeaveCriticalSection` at `0x1400041cb`
- `KERNEL32!LeaveCriticalSection` at `0x1400048f7`
- `KERNEL32!LeaveCriticalSection` at `0x1400041cb`
- `KERNEL32!LeaveCriticalSection` at `0x1400048f7`
- `KERNEL32!EnterCriticalSection` at `0x14000407c`
- `KERNEL32!EnterCriticalSection` at `0x14000407c`
- `BDEHDCFGLIB!?QueryStepPercentComplete@CDriveConfiguration@@QEAAJPEAK@Z` at `0x1400040bd`
- `BDEHDCFGLIB!?QueryStepPercentComplete@CDriveConfiguration@@QEAAJPEAK@Z` at `0x1400040bd`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400040d5`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000411a`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400040d5`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x14000411a`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::UpdateProgress(CBdeCfgConsole *this)
{
  int StepDescription; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned __int64 *v4; // r9
  signed int LastError; // eax
  unsigned int v7; // [rsp+44h] [rbp-264h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-260h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-258h] BYREF
  va_list Arguments[2]; // [rsp+60h] [rbp-248h] BYREF
  __int128 v11; // [rsp+70h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-228h] BYREF

  Block[1] = this;
  v7 = 0;
  lpSource = 0;
  Block[0] = 0;
  *(_OWORD *)Arguments = 0;
  v11 = 0;
  StepDescription = 0;
  if ( *((_DWORD *)this + 374) != -1 )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1456);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
    *((_DWORD *)this + 375) = ((unsigned __int8)*((_DWORD *)this + 375) + 1) & 3;
    StepDescription = CBdeCfgConsole::GetStepDescription(this, *((_DWORD *)this + 374), Block, v4);
    if ( StepDescription >= 0 )
    {
      if ( CDriveConfiguration::QueryStepPercentComplete((CBdeCfgConsole *)((char *)this + 72), &v7) )
      {
        StepDescription = BdeCfgLoadResourceString(0x131u, (unsigned __int16 **)&lpSource);
        if ( StepDescription >= 0 )
        {
          Arguments[0] = (va_list)Block[0];
          Arguments[1] = (va_list)*((unsigned int *)this + 375);
          *(_QWORD *)&v11 = L"...";
LABEL_8:
          if ( FormatMessageW(0x2400u, lpSource, 0, 0, Buffer, 0x104u, Arguments) )
          {
            CBdeCfgConsole::PrintProgressLine(this, Buffer);
          }
          else
          {
            LastError = GetLastError();
            StepDescription = LastError;
            if ( LastError > 0 )
              StepDescription = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      else
      {
        StepDescription = BdeCfgLoadResourceString(0x132u, (unsigned __int16 **)&lpSource);
        if ( StepDescription >= 0 )
        {
          Arguments[0] = (va_list)Block[0];
          Arguments[1] = (va_list)v7;
          *(_QWORD *)&v11 = *((unsigned int *)this + 375);
          *((_QWORD *)&v11 + 1) = L"...";
          goto LABEL_8;
        }
      }
    }
    operator delete((void *)lpSource);
    operator delete(Block[0]);
    LeaveCriticalSection(v3);
  }
  return (unsigned int)StepDescription;
}

```

## disassembly

```asm
0x140004010  mov     [rsp+arg_8], rbx
0x140004015  mov     [rsp+arg_10], rsi
0x14000401a  push    rdi
0x14000401b  sub     rsp, 2A0h
0x140004022  mov     rax, cs:__security_cookie
0x140004029  xor     rax, rsp
0x14000402c  mov     [rsp+2A8h+var_18], rax
0x140004034  mov     rdi, rcx
0x140004037  mov     [rsp+2A8h+var_250], rcx
0x14000403c  mov     [rsp+2A8h+var_264], 0
0x140004044  mov     [rsp+2A8h+lpSource], 0
0x14000404d  mov     [rsp+2A8h+Block], 0
0x140004056  xorps   xmm0, xmm0
0x140004059  movups  xmmword ptr [rsp+2A8h+var_248], xmm0
0x14000405e  movups  [rsp+2A8h+var_238], xmm0
0x140004063  xor     ebx, ebx
0x140004065  cmp     dword ptr [rcx+5D8h], 0FFFFFFFFh
0x14000406c  jz      loc_1400041D1
0x140004072  lea     rsi, [rcx+5B0h]
0x140004079  mov     rcx, rsi; lpCriticalSection
0x14000407c  call    cs:__imp_EnterCriticalSection
0x140004082  mov     eax, [rdi+5DCh]
0x140004088  inc     eax
0x14000408a  and     eax, 3
0x14000408d  mov     [rdi+5DCh], eax
0x140004093  lea     r8, [rsp+2A8h+Block]
0x140004098  mov     edx, [rdi+5D8h]
0x14000409e  mov     rcx, rdi
0x1400040a1  call    ?GetStepDescription@CBdeCfgConsole@@AEAAJW4_BDECFG_STEP_ID@@PEAPEAG@Z; CBdeCfgConsole::GetStepDescription(_BDECFG_STEP_ID,ushort * *)
0x1400040a6  mov     ebx, eax
0x1400040a8  mov     [rsp+2A8h+var_268], eax
0x1400040ac  test    eax, eax
0x1400040ae  js      loc_1400041B4
0x1400040b4  lea     rcx, [rdi+48h]
0x1400040b8  lea     rdx, [rsp+2A8h+var_264]
0x1400040bd  call    cs:__imp_?QueryStepPercentComplete@CDriveConfiguration@@QEAAJPEAK@Z; CDriveConfiguration::QueryStepPercentComplete(ulong *)
0x1400040c3  mov     [rsp+2A8h+var_268], eax
0x1400040c7  lea     rdx, [rsp+2A8h+lpSource]
0x1400040cc  test    eax, eax
0x1400040ce  jnz     short loc_140004115
0x1400040d0  mov     ecx, 132h
0x1400040d5  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x1400040db  mov     ebx, eax
0x1400040dd  mov     [rsp+2A8h+var_268], eax
0x1400040e1  test    eax, eax
0x1400040e3  js      loc_1400041B4
0x1400040e9  mov     rax, [rsp+2A8h+Block]
0x1400040ee  mov     [rsp+2A8h+var_248], rax
0x1400040f3  mov     eax, [rsp+2A8h+var_264]
0x1400040f7  mov     [rsp+2A8h+var_248+8], rax
0x1400040fc  mov     eax, [rdi+5DCh]
0x140004102  mov     qword ptr [rsp+2A8h+var_238], rax
0x140004107  lea     rax, asc_140006828; "..."
0x14000410e  mov     qword ptr [rsp+2A8h+var_238+8], rax
0x140004113  jmp     short loc_14000414F
0x140004115  mov     ecx, 131h
0x14000411a  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140004120  mov     ebx, eax
0x140004122  mov     [rsp+2A8h+var_268], eax
0x140004126  test    eax, eax
0x140004128  js      loc_1400041B4
0x14000412e  mov     rax, [rsp+2A8h+Block]
0x140004133  mov     [rsp+2A8h+var_248], rax
0x140004138  mov     eax, [rdi+5DCh]
0x14000413e  mov     [rsp+2A8h+var_248+8], rax
0x140004143  lea     rax, asc_140006828; "..."
0x14000414a  mov     qword ptr [rsp+2A8h+var_238], rax
0x14000414f  lea     rax, [rsp+2A8h+var_248]
0x140004154  mov     [rsp+2A8h+Arguments], rax; Arguments
0x140004159  mov     [rsp+2A8h+nSize], 104h; nSize
0x140004161  lea     rax, [rsp+2A8h+Buffer]
0x140004169  mov     [rsp+2A8h+lpBuffer], rax; lpBuffer
0x14000416e  xor     r9d, r9d; dwLanguageId
0x140004171  xor     r8d, r8d; dwMessageId
0x140004174  mov     rdx, [rsp+2A8h+lpSource]; lpSource
0x140004179  mov     ecx, 2400h; dwFlags
0x14000417e  call    cs:__imp_FormatMessageW
0x140004184  test    eax, eax
0x140004186  jnz     short loc_1400041A3
0x140004188  call    cs:__imp_GetLastError
0x14000418e  mov     ebx, eax
0x140004190  test    eax, eax
0x140004192  jle     short loc_14000419D
0x140004194  movzx   ebx, ax
0x140004197  or      ebx, 80070000h
0x14000419d  mov     [rsp+2A8h+var_268], ebx
0x1400041a1  jmp     short loc_1400041B4
0x1400041a3  lea     rdx, [rsp+2A8h+Buffer]; unsigned __int16 *
0x1400041ab  mov     rcx, rdi; this
0x1400041ae  call    ?PrintProgressLine@CBdeCfgConsole@@AEAAXPEBG@Z; CBdeCfgConsole::PrintProgressLine(ushort const *)
0x1400041b3  nop
0x1400041b4  mov     rcx, [rsp+2A8h+lpSource]; Block
0x1400041b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400041be  mov     rcx, [rsp+2A8h+Block]; Block
0x1400041c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400041c8  mov     rcx, rsi; lpCriticalSection
0x1400041cb  call    cs:__imp_LeaveCriticalSection
0x1400041d1  mov     eax, ebx
0x1400041d3  mov     rcx, [rsp+2A8h+var_18]
0x1400041db  xor     rcx, rsp; StackCookie
0x1400041de  call    __security_check_cookie
0x1400041e3  lea     r11, [rsp+2A8h+var_8]
0x1400041eb  mov     rbx, [r11+18h]
0x1400041ef  mov     rsi, [r11+20h]
0x1400041f3  mov     rsp, r11
0x1400041f6  pop     rdi
0x1400041f7  retn
0x1400048d1  push    rbp
0x1400048d3  sub     rsp, 40h
0x1400048d7  mov     rbp, rdx
0x1400048da  mov     rcx, [rbp+48h]; Block
0x1400048de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400048e3  mov     rcx, [rbp+50h]; Block
0x1400048e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400048ec  mov     rcx, [rbp+58h]
0x1400048f0  add     rcx, 5B0h; lpCriticalSection
0x1400048f7  call    cs:__imp_LeaveCriticalSection
0x1400048fd  nop
0x1400048fe  add     rsp, 40h
0x140004902  pop     rbp
0x140004903  retn
```
