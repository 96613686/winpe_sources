# Installersp_EventTraceFileCreate(_PCA_EVENT_ETW_FROM_DM_PARAM *)

- ea: `0x180015870`
- end: `0x180015abe`
- name: `?Installersp_EventTraceFileCreate@@YAKPEAU_PCA_EVENT_ETW_FROM_DM_PARAM@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(struct _PCA_EVENT_ETW_FROM_DM_PARAM *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c560`
- `0x180012920`
- `0x180013f34`
- `0x180013fac`
- `0x180015870`
- `0x18001b320`
- `0x180032f68`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180015a19`
- `msvcrt!_wcsnicmp` at `0x180015a98`
- `msvcrt!_wcsnicmp` at `0x180015a19`
- `msvcrt!_wcsnicmp` at `0x180015a98`
- `msvcrt!wcscat_s` at `0x1800159f2`
- `msvcrt!wcscat_s` at `0x1800159f2`
- `msvcrt!wcscpy_s` at `0x1800159dc`
- `msvcrt!wcscpy_s` at `0x1800159dc`
- `ntdll!RtlGetNtSystemRoot` at `0x1800159c5`
- `ntdll!RtlGetNtSystemRoot` at `0x1800159c5`
- `ntdll!RtlCompareMemory` at `0x180015943`
- `ntdll!RtlCompareMemory` at `0x180015943`

## string_xrefs

- `0x18001597d`: `Bad FileCreate event [%d]`
- `0x18001598a`: `Installersp_EventTraceFileCreate`
- `0x180015a78`: `Installers`
- `0x1800159e2`: `\Temp\`

## pseudocode

```c
__int64 __fastcall Installersp_EventTraceFileCreate(struct _PCA_EVENT_ETW_FROM_DM_PARAM *a1)
{
  __int64 v1; // rdx
  __int64 v3; // rdi
  _QWORD *v4; // rbx
  unsigned __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r12
  unsigned __int64 v8; // rcx
  wchar_t *v9; // r15
  wchar_t *i; // r12
  unsigned __int64 v11; // rax
  const wchar_t *NtSystemRoot; // rax
  size_t v14; // r8
  size_t v15; // r8
  unsigned __int64 ProcessIndex; // rax
  int v17; // eax
  unsigned int v18; // ebx
  struct _PCA_CHAIN *v19; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[264]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[264]; // [rsp+250h] [rbp+150h] BYREF

  v1 = *((_QWORD *)a1 + 1);
  v22 = 0;
  if ( v1 )
  {
    if ( (unsigned int)PcaChainGetSlot(&v22, v1, 3) )
    {
      v3 = v22;
      if ( *(_DWORD *)(v22 + 1420) )
      {
        if ( !*(_DWORD *)(v22 + 1468) )
        {
          v4 = (_QWORD *)*((_QWORD *)a1 + 14);
          v5 = 520;
          v6 = v4[5];
          v7 = v4[4];
          memset_0(String1, 0, 0x208u);
          v8 = v4[4];
          if ( v8 >= v4[1] )
          {
LABEL_12:
            v20 = 160;
            AslLogCallPrintf(
              1,
              (unsigned int)"Installersp_EventTraceFileCreate",
              3462,
              (unsigned int)"Bad FileCreate event [%d]",
              v20);
          }
          else
          {
            v9 = (wchar_t *)(v7 + v6);
            for ( i = String1; ; ++i )
            {
              v11 = v4[1];
              if ( v8 >= v11 )
                break;
              if ( v11 - v8 >= 2 && RtlCompareMemory(&dword_1800FF0F4, v9, 2u) == 2 )
              {
                v4[4] += 2LL;
                break;
              }
              if ( v5 < 2 )
                goto LABEL_12;
              v5 -= 2LL;
              *i = *v9++;
              v4[4] += 2LL;
              v8 = v4[4];
            }
            NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot();
            wcscpy_s(Destination, 0x104u, NtSystemRoot);
            wcscat_s(Destination, 0x104u, L"\\Temp\\");
            v14 = -1;
            do
              ++v14;
            while ( Destination[v14] );
            if ( _wcsnicmp(String1, Destination, v14) )
            {
              v15 = *(_QWORD *)(v3 + 1400);
              if ( !v15 || _wcsnicmp(String1, (const wchar_t *)(v3 + 880), v15) )
              {
                ProcessIndex = PcaChainGetProcessIndex(*((_QWORD *)a1 + 1), *((_DWORD *)a1 + 7), *((_QWORD *)a1 + 2));
                v17 = RtlStringArray::Append((RtlStringArray *)(v3 + 120), String1, ProcessIndex);
                if ( v17 )
                {
                  v21 = v17;
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"Installersp_EventTraceFileCreate",
                    3495,
                    (unsigned int)"Failed to add to trace file list [%d]",
                    v21);
                }
                else
                {
                  v18 = *((_DWORD *)a1 + 7);
                  v19 = PcapChainFromHandle(*((_QWORD *)a1 + 1));
                  PcaTracePrintf("Installers", *((_DWORD *)v19 + 4), v18, "FileTracer,File,%S", String1);
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015870  push    rbp
0x180015872  push    rbx
0x180015873  push    rsi
0x180015874  push    rdi
0x180015875  push    r12
0x180015877  push    r13
0x180015879  push    r14
0x18001587b  push    r15
0x18001587d  lea     rbp, [rsp-378h]
0x180015885  sub     rsp, 478h
0x18001588c  mov     rax, cs:__security_cookie
0x180015893  xor     rax, rsp
0x180015896  mov     [rbp+3B0h+var_50], rax
0x18001589d  mov     rdx, [rcx+8]
0x1800158a1  xor     r13d, r13d
0x1800158a4  mov     [rsp+4B0h+var_480], r13
0x1800158a9  mov     rsi, rcx
0x1800158ac  test    rdx, rdx
0x1800158af  jz      loc_18001599B
0x1800158b5  lea     r8d, [r13+3]
0x1800158b9  lea     rcx, [rsp+4B0h+var_480]
0x1800158be  call    ?PcaChainGetSlot@@YAHPEAPEAX_KW4_PCA_SLOT_ID@@@Z; PcaChainGetSlot(void * *,unsigned __int64,_PCA_SLOT_ID)
0x1800158c3  test    eax, eax
0x1800158c5  jz      loc_18001599B
0x1800158cb  mov     rdi, [rsp+4B0h+var_480]
0x1800158d0  cmp     [rdi+58Ch], r13d
0x1800158d7  jz      loc_18001599B
0x1800158dd  cmp     [rdi+5BCh], r13d
0x1800158e4  jnz     loc_18001599B
0x1800158ea  mov     rbx, [rsi+70h]
0x1800158ee  lea     rcx, [rsp+4B0h+String1]; void *
0x1800158f3  mov     r14d, 208h
0x1800158f9  xor     edx, edx; Val
0x1800158fb  mov     r8d, r14d; Size
0x1800158fe  mov     r15, [rbx+28h]
0x180015902  mov     r12, [rbx+20h]
0x180015906  call    memset_0
0x18001590b  mov     rcx, [rbx+20h]
0x18001590f  cmp     rcx, [rbx+8]
0x180015913  jnb     short loc_180015975
0x180015915  add     r15, r12
0x180015918  lea     r12, [rsp+4B0h+String1]
0x18001591d  mov     rax, [rbx+8]
0x180015921  cmp     rcx, rax
0x180015924  jnb     loc_1800159C5
0x18001592a  sub     rax, rcx
0x18001592d  cmp     rax, 2
0x180015931  jb      short loc_18001594F
0x180015933  mov     r8d, 2; Length
0x180015939  lea     rcx, dword_1800FF0F4; Source1
0x180015940  mov     rdx, r15; Source2
0x180015943  call    cs:__imp_RtlCompareMemory
0x180015949  cmp     rax, 2
0x18001594d  jz      short loc_1800159C0
0x18001594f  cmp     r14, 2
0x180015953  jb      short loc_180015975
0x180015955  movzx   eax, word ptr [r15]
0x180015959  sub     r14, 2
0x18001595d  mov     [r12], ax
0x180015962  add     r15, 2
0x180015966  add     r12, 2
0x18001596a  add     qword ptr [rbx+20h], 2
0x18001596f  mov     rcx, [rbx+20h]
0x180015973  jmp     short loc_18001591D
0x180015975  mov     [rsp+4B0h+var_490], 0A0h
0x18001597d  lea     r9, aBadFilecreateE; "Bad FileCreate event [%d]"
0x180015984  mov     r8d, 0D86h
0x18001598a  lea     rdx, aInstallerspEve_0; "Installersp_EventTraceFileCreate"
0x180015991  mov     ecx, 1
0x180015996  call    AslLogCallPrintf
0x18001599b  xor     eax, eax
0x18001599d  mov     rcx, [rbp+3B0h+var_50]
0x1800159a4  xor     rcx, rsp; StackCookie
0x1800159a7  call    __security_check_cookie
0x1800159ac  add     rsp, 478h
0x1800159b3  pop     r15
0x1800159b5  pop     r14
0x1800159b7  pop     r13
0x1800159b9  pop     r12
0x1800159bb  pop     rdi
0x1800159bc  pop     rsi
0x1800159bd  pop     rbx
0x1800159be  pop     rbp
0x1800159bf  retn
0x1800159c0  add     qword ptr [rbx+20h], 2
0x1800159c5  call    cs:__imp_RtlGetNtSystemRoot
0x1800159cb  mov     ebx, 104h
0x1800159d0  lea     rcx, [rbp+3B0h+Destination]; Destination
0x1800159d7  mov     r8, rax; Source
0x1800159da  mov     edx, ebx; SizeInWords
0x1800159dc  call    cs:__imp_wcscpy_s
0x1800159e2  lea     r8, aTemp_0; "\\Temp\\"
0x1800159e9  mov     edx, ebx; SizeInWords
0x1800159eb  lea     rcx, [rbp+3B0h+Destination]; Destination
0x1800159f2  call    cs:__imp_wcscat_s
0x1800159f8  lea     rax, [rbp+3B0h+Destination]
0x1800159ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015a03  inc     r8; MaxCount
0x180015a06  cmp     [rax+r8*2], r13w
0x180015a0b  jnz     short loc_180015A03
0x180015a0d  lea     rdx, [rbp+3B0h+Destination]; String2
0x180015a14  lea     rcx, [rsp+4B0h+String1]; String1
0x180015a19  call    cs:__imp__wcsnicmp
0x180015a1f  test    eax, eax
0x180015a21  jz      loc_18001599B
0x180015a27  mov     r8, [rdi+578h]; MaxCount
0x180015a2e  test    r8, r8
0x180015a31  jnz     short loc_180015A8C
0x180015a33  mov     r8, [rsi+10h]; unsigned __int64
0x180015a37  mov     edx, [rsi+1Ch]; unsigned int
0x180015a3a  mov     rcx, [rsi+8]; unsigned __int64
0x180015a3e  call    ?PcaChainGetProcessIndex@@YA_K_KK0@Z; PcaChainGetProcessIndex(unsigned __int64,ulong,unsigned __int64)
0x180015a43  lea     rcx, [rdi+78h]; this
0x180015a47  mov     r8, rax; unsigned __int64
0x180015a4a  lea     rdx, [rsp+4B0h+String1]; unsigned __int16 *
0x180015a4f  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x180015a54  test    eax, eax
0x180015a56  jnz     short loc_180015AA8
0x180015a58  mov     rcx, [rsi+8]; unsigned __int64
0x180015a5c  mov     ebx, [rsi+1Ch]
0x180015a5f  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180015a64  lea     rcx, [rsp+4B0h+String1]
0x180015a69  mov     r8d, ebx; unsigned int
0x180015a6c  mov     qword ptr [rsp+4B0h+var_490], rcx
0x180015a71  lea     r9, aFiletracerFile; "FileTracer,File,%S"
0x180015a78  lea     rcx, aInstallers; "Installers"
0x180015a7f  mov     edx, [rax+10h]; unsigned int
0x180015a82  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180015a87  jmp     loc_18001599B
0x180015a8c  lea     rdx, [rdi+370h]; String2
0x180015a93  lea     rcx, [rsp+4B0h+String1]; String1
0x180015a98  call    cs:__imp__wcsnicmp
0x180015a9e  test    eax, eax
0x180015aa0  jz      loc_18001599B
0x180015aa6  jmp     short loc_180015A33
0x180015aa8  mov     [rsp+4B0h+var_490], eax
0x180015aac  lea     r9, aFailedToAddToT; "Failed to add to trace file list [%d]"
0x180015ab3  mov     r8d, 0DA7h
0x180015ab9  jmp     loc_18001598A
```
