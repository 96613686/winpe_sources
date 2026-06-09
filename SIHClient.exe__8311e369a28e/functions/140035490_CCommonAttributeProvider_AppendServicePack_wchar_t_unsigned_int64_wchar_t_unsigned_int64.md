# CCommonAttributeProvider::AppendServicePack(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x140035490`
- end: `0x1400356a6`
- name: `?AppendServicePack@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct _OSVERSIONINFOW **this, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140034ccc`

## callees

- `0x140007780`
- `0x14000cdb8`
- `0x14000ce30`
- `0x1400154b4`
- `0x140033160`
- `0x140035490`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003553a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003553a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140035530`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140035530`

## string_xrefs

- `0x140035580`: `CCommonAttributeProvider::GetOSVersionInfoEx`
- `0x140035673`: `CCommonAttributeProvider::AppendServicePack`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCommonAttributeProvider::AppendServicePack(
        struct _OSVERSIONINFOW **this,
        wchar_t *a2,
        unsigned __int64 a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  struct _OSVERSIONINFOW *v9; // rbx
  struct _OSVERSIONINFOW *v10; // rax
  signed int v11; // edi
  signed int LastError; // eax
  __int64 v13; // rax
  _WORD *v14; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rax
  wchar_t **v24; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+30h] [rbp-D0h]
  _WORD v26[144]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v27; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v28; // [rsp+168h] [rbp+68h] BYREF
  wchar_t Buffer[8]; // [rsp+170h] [rbp+70h] BYREF
  int v30; // [rsp+180h] [rbp+80h]
  __int16 v31; // [rsp+184h] [rbp+84h]

  v27 = a2;
  v28 = a3;
  memset(v26, 0, 0x11Cu);
  *a4 = a2;
  *a5 = a3;
  v9 = *this;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)Buffer = 0;
  if ( !v9 )
  {
    v10 = (struct _OSVERSIONINFOW *)SusAlloc(0x11Cu);
    v9 = v10;
    if ( !v10 )
    {
      v11 = -2147024882;
LABEL_9:
      SusFree(v9);
      memset(v26, 0, 0x11Cu);
      LODWORD(v24) = v11;
      WUTrace("CCommonAttributeProvider::GetOSVersionInfoEx", 88, 4, 1, v24, L"Method failed");
LABEL_15:
      LODWORD(v24) = v11;
      WUTrace("CCommonAttributeProvider::AppendServicePack", 345, 4, 1, v24, L"Method failed");
      return (unsigned int)v11;
    }
    v10->dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(v10) )
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 >= 0 )
        v11 = -2147418113;
      goto LABEL_9;
    }
    *this = v9;
  }
  v13 = 2;
  v14 = v26;
  do
  {
    v15 = *(_OWORD *)&v9->dwPlatformId;
    *(_OWORD *)v14 = *(_OWORD *)&v9->dwOSVersionInfoSize;
    v16 = *(_OWORD *)&v9->szCSDVersion[6];
    *((_OWORD *)v14 + 1) = v15;
    v17 = *(_OWORD *)&v9->szCSDVersion[14];
    *((_OWORD *)v14 + 2) = v16;
    v18 = *(_OWORD *)&v9->szCSDVersion[22];
    *((_OWORD *)v14 + 3) = v17;
    v19 = *(_OWORD *)&v9->szCSDVersion[30];
    *((_OWORD *)v14 + 4) = v18;
    v20 = *(_OWORD *)&v9->szCSDVersion[38];
    *((_OWORD *)v14 + 5) = v19;
    v21 = *(_OWORD *)&v9->szCSDVersion[46];
    v9 = (struct _OSVERSIONINFOW *)((char *)v9 + 128);
    *((_OWORD *)v14 + 6) = v20;
    v14 += 64;
    *((_OWORD *)v14 - 1) = v21;
    --v13;
  }
  while ( v13 );
  v22 = *(_QWORD *)&v9->dwPlatformId;
  *(_OWORD *)v14 = *(_OWORD *)&v9->dwOSVersionInfoSize;
  *((_QWORD *)v14 + 2) = v22;
  *((_DWORD *)v14 + 6) = *(_DWORD *)&v9->szCSDVersion[2];
  v11 = StringCchPrintfW(Buffer, 0xBu, L"%ld", v26[138]);
  if ( v11 < 0 )
    goto LABEL_15;
  v11 = StringCchCatNExW(a2, a3, Buffer, 0xAu, &v27, &v28, v25);
  if ( v11 < 0 )
    goto LABEL_15;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140035490  push    rbp
0x140035492  push    rbx
0x140035493  push    rsi
0x140035494  push    rdi
0x140035495  push    r12
0x140035497  push    r14
0x140035499  push    r15
0x14003549b  lea     rbp, [rsp-90h]
0x1400354a3  sub     rsp, 190h
0x1400354aa  mov     rax, cs:__security_cookie
0x1400354b1  xor     rax, rsp
0x1400354b4  mov     [rbp+0C0h+var_38], rax
0x1400354bb  mov     rbx, [rbp+0C0h+arg_20]
0x1400354c2  mov     r15, r8
0x1400354c5  mov     r14, rdx
0x1400354c8  mov     [rbp+0C0h+var_60], rdx
0x1400354cc  mov     rsi, rcx
0x1400354cf  mov     [rbp+0C0h+var_58], r8
0x1400354d3  mov     r12d, 11Ch
0x1400354d9  lea     rcx, [rsp+1C0h+var_180]; void *
0x1400354de  mov     r8d, r12d; Size
0x1400354e1  xor     edx, edx; Val
0x1400354e3  mov     rdi, r9
0x1400354e6  call    memset
0x1400354eb  xor     eax, eax
0x1400354ed  mov     [rdi], r14
0x1400354f0  mov     [rbx], r15
0x1400354f3  xorps   xmm0, xmm0
0x1400354f6  mov     rbx, [rsi]
0x1400354f9  mov     [rbp+0C0h+var_40], eax
0x1400354ff  mov     [rbp+0C0h+var_3C], ax
0x140035506  movups  xmmword ptr [rbp+0C0h+Buffer], xmm0
0x14003550a  test    rbx, rbx
0x14003550d  jnz     loc_1400355A0
0x140035513  mov     ecx, r12d; unsigned __int64
0x140035516  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x14003551b  mov     rbx, rax
0x14003551e  test    rax, rax
0x140035521  jnz     short loc_14003552A
0x140035523  mov     edi, 8007000Eh
0x140035528  jmp     short loc_140035558
0x14003552a  mov     rcx, rbx; lpVersionInformation
0x14003552d  mov     [rax], r12d
0x140035530  call    cs:__imp_GetVersionExW
0x140035536  test    eax, eax
0x140035538  jnz     short loc_14003559D
0x14003553a  call    cs:__imp_GetLastError
0x140035540  movzx   edi, ax
0x140035543  or      edi, 80070000h
0x140035549  test    eax, eax
0x14003554b  cmovle  edi, eax
0x14003554e  mov     eax, 8000FFFFh
0x140035553  test    edi, edi
0x140035555  cmovns  edi, eax
0x140035558  mov     rcx, rbx; lpMem
0x14003555b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140035560  mov     r8, r12; Size
0x140035563  lea     rcx, [rsp+1C0h+var_180]; void *
0x140035568  xor     edx, edx; Val
0x14003556a  call    memset
0x14003556f  mov     edx, 58h ; 'X'
0x140035574  lea     rbx, aMethodFailed; "Method failed"
0x14003557b  mov     [rsp+1C0h+var_198], rbx
0x140035580  lea     rcx, aCcommonattribu_5; "CCommonAttributeProvider::GetOSVersionI"...
0x140035587  mov     dword ptr [rsp+1C0h+var_1A0], edi
0x14003558b  lea     r9d, [rdx-57h]
0x14003558f  lea     r8d, [rdx-54h]
0x140035593  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140035598  jmp     loc_14003565F
0x14003559d  mov     [rsi], rbx
0x1400355a0  mov     eax, 2
0x1400355a5  lea     rcx, [rsp+1C0h+var_180]
0x1400355aa  lea     edx, [rax+7Eh]
0x1400355ad  movups  xmm0, xmmword ptr [rbx]
0x1400355b0  movups  xmm1, xmmword ptr [rbx+10h]
0x1400355b4  movups  xmmword ptr [rcx], xmm0
0x1400355b7  movups  xmm0, xmmword ptr [rbx+20h]
0x1400355bb  movups  xmmword ptr [rcx+10h], xmm1
0x1400355bf  movups  xmm1, xmmword ptr [rbx+30h]
0x1400355c3  movups  xmmword ptr [rcx+20h], xmm0
0x1400355c7  movups  xmm0, xmmword ptr [rbx+40h]
0x1400355cb  movups  xmmword ptr [rcx+30h], xmm1
0x1400355cf  movups  xmm1, xmmword ptr [rbx+50h]
0x1400355d3  movups  xmmword ptr [rcx+40h], xmm0
0x1400355d7  movups  xmm0, xmmword ptr [rbx+60h]
0x1400355db  movups  xmmword ptr [rcx+50h], xmm1
0x1400355df  movups  xmm1, xmmword ptr [rbx+70h]
0x1400355e3  add     rbx, rdx
0x1400355e6  movups  xmmword ptr [rcx+60h], xmm0
0x1400355ea  add     rcx, rdx
0x1400355ed  movups  xmmword ptr [rcx-10h], xmm1
0x1400355f1  sub     rax, 1
0x1400355f5  jnz     short loc_1400355AD
0x1400355f7  mov     rax, [rbx+10h]
0x1400355fb  lea     r8, aLd; "%ld"
0x140035602  movups  xmm0, xmmword ptr [rbx]
0x140035605  mov     edx, 0Bh; unsigned __int64
0x14003560a  movups  xmmword ptr [rcx], xmm0
0x14003560d  mov     [rcx+10h], rax
0x140035611  mov     eax, [rbx+18h]
0x140035614  mov     [rcx+18h], eax
0x140035617  lea     rcx, [rbp+0C0h+Buffer]; Buffer
0x14003561b  movzx   r9d, [rbp+0C0h+var_6C]
0x140035620  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140035625  mov     edi, eax
0x140035627  test    eax, eax
0x140035629  js      short loc_140035658
0x14003562b  lea     rax, [rbp+0C0h+var_58]
0x14003562f  mov     r9d, 0Ah; unsigned __int64
0x140035635  mov     [rsp+1C0h+var_198], rax; unsigned __int64 *
0x14003563a  lea     r8, [rbp+0C0h+Buffer]; wchar_t *
0x14003563e  lea     rax, [rbp+0C0h+var_60]
0x140035642  mov     rdx, r15; unsigned __int64
0x140035645  mov     rcx, r14; wchar_t *
0x140035648  mov     [rsp+1C0h+var_1A0], rax; wchar_t **
0x14003564d  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035652  mov     edi, eax
0x140035654  test    eax, eax
0x140035656  jns     short loc_140035683
0x140035658  lea     rbx, aMethodFailed; "Method failed"
0x14003565f  mov     r9d, 1
0x140035665  mov     [rsp+1C0h+var_198], rbx
0x14003566a  mov     edx, 159h
0x14003566f  mov     dword ptr [rsp+1C0h+var_1A0], edi
0x140035673  lea     rcx, aCcommonattribu_1; "CCommonAttributeProvider::AppendService"...
0x14003567a  lea     r8d, [r9+3]
0x14003567e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140035683  mov     eax, edi
0x140035685  mov     rcx, [rbp+0C0h+var_38]
0x14003568c  xor     rcx, rsp; StackCookie
0x14003568f  call    __security_check_cookie
0x140035694  add     rsp, 190h
0x14003569b  pop     r15
0x14003569d  pop     r14
0x14003569f  pop     r12
0x1400356a1  pop     rdi
0x1400356a2  pop     rsi
0x1400356a3  pop     rbx
0x1400356a4  pop     rbp
0x1400356a5  retn
```
