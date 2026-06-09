# CWMIBinMof::UseDefaultLocaleId(ushort *,ushort &)

- ea: `0x180019520`
- end: `0x1800196f7`
- name: `?UseDefaultLocaleId@CWMIBinMof@@AEAAHPEAGAEAG@Z`
- size: `471`
- prototype: `int(CWMIBinMof *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800186bc`

## callees

- `0x1800021f0`
- `0x1800039f4`
- `0x180004120`
- `0x1800079f0`
- `0x1800170f8`
- `0x180018654`
- `0x180019520`

## import_xrefs

- `msvcrt!_wtoi` at `0x180019658`
- `msvcrt!_wtoi` at `0x180019658`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180019568`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800195b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180019568`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800195b4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019586`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800196d8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019586`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800196d8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001954b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001959d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001954b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001959d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWMIBinMof::UseDefaultLocaleId(wchar_t *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v5; // esi
  WCHAR *v6; // rax
  WCHAR *v7; // rbp
  UINT WindowsDirectoryW; // eax
  UINT v9; // edi
  unsigned __int64 v10; // rbx
  UINT v11; // edi
  WCHAR *v12; // rax
  unsigned __int16 *v13; // rdi
  wchar_t *v14; // rbx
  CWMIBinMof *v15; // rcx
  int v16; // r9d
  CWMIBinMof *v17; // rcx
  int v18; // r9d
  CWMIBinMof *v19; // rcx
  int v20; // r9d
  CWMIBinMof *v21; // rcx
  int v22; // r9d
  wchar_t *String; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v25; // [rsp+68h] [rbp+20h] BYREF

  String = this;
  v5 = 1;
  v6 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v7 = v6;
  if ( v6 )
  {
    WindowsDirectoryW = GetWindowsDirectoryW(v6, 0x105u);
    v9 = WindowsDirectoryW;
    if ( !WindowsDirectoryW )
      goto LABEL_21;
    v10 = -1;
    if ( WindowsDirectoryW <= 0x104 )
      goto LABEL_6;
    CWin32DefaultArena::WbemMemFree(v7);
    v11 = v9 + 1;
    v12 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v11, 2u));
    v7 = v12;
    if ( v12 )
    {
      if ( GetWindowsDirectoryW(v12, v11) )
      {
        do
LABEL_6:
          ++v10;
        while ( v7[v10] );
        if ( !(unsigned int)wbem_wcsnicmp(v7, a2, v10) )
        {
          CAutoWChar::CAutoWChar((CAutoWChar *)&v25, 260);
          CAutoWChar::CAutoWChar((CAutoWChar *)&String, 260);
          v13 = v25;
          if ( v25 )
          {
            v14 = String;
            if ( String )
            {
              if ( (int)StringCchCopyW(v25, 0x104u, a2) >= 0 )
              {
                if ( CWMIBinMof::GetNextSectionFromTheEnd(v15, v13, v14, v16) )
                {
                  if ( CWMIBinMof::GetNextSectionFromTheEnd(v17, v13, v14, v18) )
                  {
                    *a3 = _wtoi(v14);
                    if ( CWMIBinMof::GetNextSectionFromTheEnd(v19, v13, v14, v20) )
                    {
                      if ( (unsigned int)wbem_wcsicmp(L"MUI", v14) )
                      {
                        if ( !(unsigned int)wbem_wcsicmp(L"Fallback", v14)
                          && CWMIBinMof::GetNextSectionFromTheEnd(v21, v13, v14, v22)
                          && !(unsigned int)wbem_wcsicmp(L"MUI", v14) )
                        {
                          v5 = 0;
                        }
                      }
                      else
                      {
                        v5 = 0;
                      }
                    }
                  }
                }
              }
            }
          }
          CAutoWChar::~CAutoWChar((CAutoWChar *)&String);
          CAutoWChar::~CAutoWChar((CAutoWChar *)&v25);
        }
      }
LABEL_21:
      CWin32DefaultArena::WbemMemFree(v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180019520  mov     [rsp+arg_8], rbx
0x180019525  mov     [rsp+arg_10], rbp
0x18001952a  mov     [rsp+String], rcx
0x18001952f  push    rsi
0x180019530  push    rdi
0x180019531  push    r12
0x180019533  push    r14
0x180019535  push    r15
0x180019537  sub     rsp, 20h
0x18001953b  mov     r15, r8
0x18001953e  mov     r14, rdx
0x180019541  mov     esi, 1
0x180019546  mov     ecx, 20Ah
0x18001954b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180019551  mov     rbp, rax
0x180019554  xor     r12d, r12d
0x180019557  test    rax, rax
0x18001955a  jz      loc_1800196DE
0x180019560  mov     edx, 105h; uSize
0x180019565  mov     rcx, rax; lpBuffer
0x180019568  call    cs:__imp_GetWindowsDirectoryW
0x18001956e  mov     edi, eax
0x180019570  test    eax, eax
0x180019572  jz      loc_1800196D5
0x180019578  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001957c  cmp     eax, 104h
0x180019581  jbe     short loc_1800195C2
0x180019583  mov     rcx, rbp
0x180019586  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001958c  inc     edi
0x18001958e  mov     ecx, edi
0x180019590  lea     eax, [rsi+1]
0x180019593  mul     rcx
0x180019596  cmovb   rax, rbx
0x18001959a  mov     rcx, rax
0x18001959d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800195a3  mov     rbp, rax
0x1800195a6  test    rax, rax
0x1800195a9  jz      loc_1800196DE
0x1800195af  mov     edx, edi; uSize
0x1800195b1  mov     rcx, rax; lpBuffer
0x1800195b4  call    cs:__imp_GetWindowsDirectoryW
0x1800195ba  test    eax, eax
0x1800195bc  jz      loc_1800196D5
0x1800195c2  inc     rbx
0x1800195c5  cmp     [rbp+rbx*2+0], r12w
0x1800195cb  jnz     short loc_1800195C2
0x1800195cd  mov     r8, rbx; unsigned __int64
0x1800195d0  mov     rdx, r14; unsigned __int16 *
0x1800195d3  mov     rcx, rbp; unsigned __int16 *
0x1800195d6  call    ?wbem_wcsnicmp@@YAHPEBG0_K@Z; wbem_wcsnicmp(ushort const *,ushort const *,unsigned __int64)
0x1800195db  test    eax, eax
0x1800195dd  jnz     loc_1800196D5
0x1800195e3  mov     edx, 104h; int
0x1800195e8  lea     rcx, [rsp+48h+arg_18]; this
0x1800195ed  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x1800195f2  nop
0x1800195f3  mov     edx, 104h; int
0x1800195f8  lea     rcx, [rsp+48h+String]; this
0x1800195fd  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x180019602  nop
0x180019603  mov     rdi, [rsp+48h+arg_18]
0x180019608  test    rdi, rdi
0x18001960b  jz      loc_1800196C0
0x180019611  mov     rbx, [rsp+48h+String]
0x180019616  test    rbx, rbx
0x180019619  jz      loc_1800196C0
0x18001961f  mov     r8, r14; unsigned __int16 *
0x180019622  mov     edx, 104h; unsigned __int64
0x180019627  mov     rcx, rdi; unsigned __int16 *
0x18001962a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001962f  test    eax, eax
0x180019631  js      loc_1800196C0
0x180019637  mov     r8, rbx; unsigned __int16 *
0x18001963a  mov     rdx, rdi; unsigned __int16 *
0x18001963d  call    ?GetNextSectionFromTheEnd@CWMIBinMof@@AEAAHPEAG0H@Z; CWMIBinMof::GetNextSectionFromTheEnd(ushort *,ushort *,int)
0x180019642  test    eax, eax
0x180019644  jz      short loc_1800196C0
0x180019646  mov     r8, rbx; unsigned __int16 *
0x180019649  mov     rdx, rdi; unsigned __int16 *
0x18001964c  call    ?GetNextSectionFromTheEnd@CWMIBinMof@@AEAAHPEAG0H@Z; CWMIBinMof::GetNextSectionFromTheEnd(ushort *,ushort *,int)
0x180019651  test    eax, eax
0x180019653  jz      short loc_1800196C0
0x180019655  mov     rcx, rbx; String
0x180019658  call    cs:__imp__wtoi
0x18001965e  mov     [r15], ax
0x180019662  mov     r8, rbx; unsigned __int16 *
0x180019665  mov     rdx, rdi; unsigned __int16 *
0x180019668  call    ?GetNextSectionFromTheEnd@CWMIBinMof@@AEAAHPEAG0H@Z; CWMIBinMof::GetNextSectionFromTheEnd(ushort *,ushort *,int)
0x18001966d  test    eax, eax
0x18001966f  jz      short loc_1800196C0
0x180019671  mov     rdx, rbx; unsigned __int16 *
0x180019674  lea     rcx, aMui; "MUI"
0x18001967b  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180019680  test    eax, eax
0x180019682  jnz     short loc_180019689
0x180019684  mov     esi, r12d
0x180019687  jmp     short loc_1800196C0
0x180019689  mov     rdx, rbx; unsigned __int16 *
0x18001968c  lea     rcx, aFallback; "Fallback"
0x180019693  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180019698  test    eax, eax
0x18001969a  jnz     short loc_1800196C0
0x18001969c  mov     r8, rbx; unsigned __int16 *
0x18001969f  mov     rdx, rdi; unsigned __int16 *
0x1800196a2  call    ?GetNextSectionFromTheEnd@CWMIBinMof@@AEAAHPEAG0H@Z; CWMIBinMof::GetNextSectionFromTheEnd(ushort *,ushort *,int)
0x1800196a7  test    eax, eax
0x1800196a9  jz      short loc_1800196C0
0x1800196ab  mov     rdx, rbx; unsigned __int16 *
0x1800196ae  lea     rcx, aMui; "MUI"
0x1800196b5  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800196ba  test    eax, eax
0x1800196bc  cmovz   esi, r12d
0x1800196c0  lea     rcx, [rsp+48h+String]; this
0x1800196c5  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x1800196ca  nop
0x1800196cb  lea     rcx, [rsp+48h+arg_18]; this
0x1800196d0  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x1800196d5  mov     rcx, rbp
0x1800196d8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800196de  mov     eax, esi
0x1800196e0  mov     rbx, [rsp+48h+arg_8]
0x1800196e5  mov     rbp, [rsp+48h+arg_10]
0x1800196ea  add     rsp, 20h
0x1800196ee  pop     r15
0x1800196f0  pop     r14
0x1800196f2  pop     r12
0x1800196f4  pop     rdi
0x1800196f5  pop     rsi
0x1800196f6  retn
```
