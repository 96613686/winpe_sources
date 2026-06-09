# CTieredVolume::SetupNames(void)

- ea: `0x140015ff0`
- end: `0x1400163ba`
- name: `?SetupNames@CTieredVolume@@AEAAJXZ`
- size: `970`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400127dc`

## callees

- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000a490`
- `0x14000b7f8`
- `0x140015648`
- `0x140015ff0`
- `0x140017708`
- `0x140017930`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x140016161`
- `msvcrt!_snwprintf_s` at `0x140016161`
- `msvcrt!malloc` at `0x1400160fa`
- `msvcrt!malloc` at `0x1400160fa`
- `msvcrt!free` at `0x140016075`
- `msvcrt!free` at `0x140016096`
- `msvcrt!free` at `0x140016075`
- `msvcrt!free` at `0x140016096`
- `ntdll!RtlStringFromGUID` at `0x1400161e2`
- `ntdll!RtlStringFromGUID` at `0x1400161e2`
- `ntdll!RtlInitUnicodeString` at `0x1400161c3`
- `ntdll!RtlInitUnicodeString` at `0x1400161c3`
- `ntdll!RtlCompareMemory` at `0x1400160c2`
- `ntdll!RtlCompareMemory` at `0x1400160c2`

## pseudocode

```c
__int64 __fastcall CTieredVolume::SetupNames(CTieredVolume *this)
{
  struct _UNICODE_STRING v2; // xmm6
  PCWSTR *v3; // rbx
  void *v4; // rcx
  struct _UNICODE_STRING *v5; // r14
  void *v6; // rcx
  int v7; // r15d
  int v8; // esi
  wchar_t *v9; // rax
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int16 v14; // ax
  int v15; // eax
  int v16; // eax
  struct _UNICODE_STRING v17; // xmm0
  __int16 v19; // [rsp+38h] [rbp-D0h] BYREF
  int v20; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+48h] [rbp-C0h]
  struct _UNICODE_STRING GuidString; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v23[5]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v24; // [rsp+88h] [rbp-80h]
  int v25; // [rsp+8Ch] [rbp-7Ch]
  char v26; // [rsp+98h] [rbp-70h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::SetupNames";
  CHResultImp::CHResultImp((CHResultImp *)&v20);
  v2 = NullUnicodeString;
  v3 = (PCWSTR *)((char *)this + 664);
  *(_QWORD *)&GuidString.Length = 5111808;
  v4 = (void *)*((_QWORD *)this + 83);
  GuidString.Buffer = (PWSTR)&v26;
  v5 = (struct _UNICODE_STRING *)((char *)this + 144);
  if ( v4 )
  {
    *v5 = NullUnicodeString;
    free(v4);
    *v3 = 0;
  }
  v6 = (void *)*((_QWORD *)this + 86);
  *(struct _UNICODE_STRING *)((char *)this + 696) = v2;
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 86) = 0;
  }
  if ( RtlCompareMemory((char *)this + 792, &NullGuid, 8u) == 8 )
  {
    v7 = *((_DWORD *)this + 196);
    v8 = *((_DWORD *)this + 197);
    *((_DWORD *)this + 200) = v7;
    *((_DWORD *)this + 201) = v8;
    v9 = (wchar_t *)malloc(0x92u);
    *v3 = v9;
    if ( !v9 )
    {
      v10 = -2147024882;
      LODWORD(v21) = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 153;
LABEL_24:
        WPP_SF_Dd(v11[2], v12, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, *((unsigned int *)this + 32), v10);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    if ( _snwprintf_s(v9, 0x48u, 0x48u, L"\\??\\GLOBALROOT\\Device\\HardDisk%u\\ClusterPartition%u\\", v7, v8) == -1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          *((unsigned int *)this + 32),
          v21);
      }
      v10 = -2147024882;
      LODWORD(v21) = -2147024882;
      goto LABEL_40;
    }
    RtlInitUnicodeString((PUNICODE_STRING)this + 9, *v3);
    v10 = v21;
  }
  else
  {
    *((_QWORD *)this + 100) = -1;
    RtlStringFromGUID((const GUID *const)this + 49, &GuidString);
    v10 = CopyUnicodeStringToBuffer(
            (struct _UNICODE_STRING *)&VolumeNamePrefix,
            &GuidString,
            (struct _UNICODE_STRING *)&BackslashString,
            (struct _UNICODE_STRING *)this + 9,
            (__int64)this + 664);
    LODWORD(v21) = v10;
  }
  if ( v10 >= 0 )
  {
    *((struct _UNICODE_STRING *)this + 42) = *v5;
    *((_WORD *)this + 336) -= 2;
    v14 = *((_WORD *)this + 336);
    if ( (Microsoft_Windows_Storage_TieringEnableBits & 1) != 0 )
    {
      v19 = v14 >> 1;
      v23[2] = &v19;
      v23[4] = *((_QWORD *)this + 85);
      v23[3] = 2;
      v24 = 2 * (v14 >> 1);
      v25 = 0;
      v15 = McGenEventWrite_EventWriteTransfer(v24, TIERENGINE_EVENT_MONITORING_VOLUME, v13, 3, v23);
    }
    else
    {
      v15 = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        v15,
        (__int64)this + 672);
    }
    if ( *((_DWORD *)this + 200) == -1
      && *((_DWORD *)this + 201) == -1
      && (v16 = CTieredVolume::SetupJetFileNames(this, (struct _UNICODE_STRING *)this + 9),
          LODWORD(v21) = v16,
          v10 = v16,
          v16 < 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 144,
          v16);
      }
    }
    else
    {
      v17 = *v5;
      LODWORD(v21) = 0;
      v10 = 0;
      *(struct _UNICODE_STRING *)((char *)this + 696) = v17;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 155;
      goto LABEL_24;
    }
  }
LABEL_40:
  CHResultImp::~CHResultImp((CHResultImp *)&v20);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140015ff0  mov     rax, rsp
0x140015ff3  push    rbp
0x140015ff4  push    rbx
0x140015ff5  push    rsi
0x140015ff6  push    rdi
0x140015ff7  push    r14
0x140015ff9  push    r15
0x140015ffb  lea     rbp, [rax-38h]
0x140015fff  sub     rsp, 108h
0x140016006  movaps  xmmword ptr [rax-48h], xmm6
0x14001600a  mov     rax, cs:__security_cookie
0x140016011  xor     rax, rsp
0x140016014  mov     [rbp+30h+var_50], rax
0x140016018  mov     rax, gs:58h
0x140016021  mov     rdi, rcx
0x140016024  mov     edx, 8
0x140016029  mov     rcx, [rax]
0x14001602c  lea     rax, aCtieredvolumeS_1; "CTieredVolume::SetupNames"
0x140016033  mov     [rdx+rcx], rax
0x140016037  lea     rcx, [rsp+130h+var_F8]; this
0x14001603c  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140016041  movups  xmm6, cs:?NullUnicodeString@@3U_UNICODE_STRING@@A; _UNICODE_STRING NullUnicodeString
0x140016048  lea     rbx, [rdi+298h]
0x14001604f  mov     qword ptr [rsp+130h+GuidString.Length], 4E0000h
0x140016058  mov     rcx, [rbx]; Block
0x14001605b  lea     rax, [rbp+30h+var_A0]
0x14001605f  mov     [rsp+130h+GuidString.Buffer], rax
0x140016064  lea     r14, [rdi+90h]
0x14001606b  test    rcx, rcx
0x14001606e  jz      short loc_140016082
0x140016070  movdqu  xmmword ptr [r14], xmm6
0x140016075  call    cs:__imp_free
0x14001607b  mov     qword ptr [rbx], 0
0x140016082  mov     rcx, [rdi+2B0h]; Block
0x140016089  movdqu  xmmword ptr [rdi+2B8h], xmm6
0x140016091  test    rcx, rcx
0x140016094  jz      short loc_1400160A7
0x140016096  call    cs:__imp_free
0x14001609c  mov     qword ptr [rdi+2B0h], 0
0x1400160a7  lea     rcx, [rdi+318h]; Source1
0x1400160ae  mov     r8d, 8; Length
0x1400160b4  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x1400160bb  lea     rsi, [rdi+310h]
0x1400160c2  call    cs:__imp_RtlCompareMemory
0x1400160c8  cmp     rax, 8
0x1400160cc  jnz     loc_1400161CF
0x1400160d2  mov     r15d, [rsi]
0x1400160d5  mov     ecx, 92h; Size
0x1400160da  movzx   eax, word ptr [rdi+314h]
0x1400160e1  movzx   esi, word ptr [rdi+316h]
0x1400160e8  shl     esi, 10h
0x1400160eb  or      esi, eax
0x1400160ed  mov     [rdi+320h], r15d
0x1400160f4  mov     [rdi+324h], esi
0x1400160fa  call    cs:__imp_malloc
0x140016100  mov     [rbx], rax
0x140016103  test    rax, rax
0x140016106  jnz     short loc_140016146
0x140016108  mov     ebx, 8007000Eh
0x14001610d  mov     dword ptr [rsp+130h+var_F0], ebx
0x140016111  mov     rcx, cs:WPP_GLOBAL_Control
0x140016118  lea     rsi, WPP_GLOBAL_Control
0x14001611f  cmp     rcx, rsi
0x140016122  jz      loc_14001638A
0x140016128  test    byte ptr [rcx+1Ch], 1
0x14001612c  jz      loc_14001638A
0x140016132  cmp     byte ptr [rcx+19h], 2
0x140016136  jb      loc_14001638A
0x14001613c  mov     edx, 99h
0x140016141  jmp     loc_140016242
0x140016146  mov     edx, 48h ; 'H'; BufferCount
0x14001614b  mov     dword ptr [rsp+130h+var_108], esi
0x14001614f  mov     r8d, edx; MaxCount
0x140016152  mov     dword ptr [rsp+130h+var_110], r15d
0x140016157  lea     r9, aGlobalrootDevi; "\\??\\GLOBALROOT\\Device\\HardDisk%u\\C"...
0x14001615e  mov     rcx, rax; Buffer
0x140016161  call    cs:__imp__snwprintf_s
0x140016167  cmp     eax, 0FFFFFFFFh
0x14001616a  jnz     short loc_1400161BD
0x14001616c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016173  lea     rsi, WPP_GLOBAL_Control
0x14001617a  cmp     rcx, rsi
0x14001617d  jz      short loc_1400161AF
0x14001617f  test    byte ptr [rcx+1Ch], 1
0x140016183  jz      short loc_1400161AF
0x140016185  cmp     byte ptr [rcx+19h], 2
0x140016189  jb      short loc_1400161AF
0x14001618b  mov     eax, dword ptr [rsp+130h+var_F0]
0x14001618f  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016196  mov     r9d, [rdi+80h]
0x14001619d  mov     edx, 9Ah
0x1400161a2  mov     rcx, [rcx+10h]
0x1400161a6  mov     dword ptr [rsp+130h+var_110], eax
0x1400161aa  call    WPP_SF_Dd
0x1400161af  mov     ebx, 8007000Eh
0x1400161b4  mov     dword ptr [rsp+130h+var_F0], ebx
0x1400161b8  jmp     loc_14001638A
0x1400161bd  mov     rdx, [rbx]; SourceString
0x1400161c0  mov     rcx, r14; DestinationString
0x1400161c3  call    cs:__imp_RtlInitUnicodeString
0x1400161c9  mov     ebx, dword ptr [rsp+130h+var_F0]
0x1400161cd  jmp     short loc_14001620E
0x1400161cf  lea     rdx, [rsp+130h+GuidString]; GuidString
0x1400161d4  mov     qword ptr [rdi+320h], 0FFFFFFFFFFFFFFFFh
0x1400161df  mov     rcx, rsi; Guid
0x1400161e2  call    cs:__imp_RtlStringFromGUID
0x1400161e8  mov     r9, r14; struct _UNICODE_STRING *
0x1400161eb  mov     [rsp+130h+var_110], rbx; __int64
0x1400161f0  lea     r8, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1400161f7  lea     rdx, [rsp+130h+GuidString]; struct _UNICODE_STRING *
0x1400161fc  lea     rcx, ?VolumeNamePrefix@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x140016203  call    ?CopyUnicodeStringToBuffer@@YAJPEBU_UNICODE_STRING@@00PEAU1@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z; CopyUnicodeStringToBuffer(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)
0x140016208  mov     ebx, eax
0x14001620a  mov     dword ptr [rsp+130h+var_F0], eax
0x14001620e  test    ebx, ebx
0x140016210  jns     short loc_140016262
0x140016212  mov     rcx, cs:WPP_GLOBAL_Control
0x140016219  lea     rsi, WPP_GLOBAL_Control
0x140016220  cmp     rcx, rsi
0x140016223  jz      loc_14001638A
0x140016229  test    byte ptr [rcx+1Ch], 1
0x14001622d  jz      loc_14001638A
0x140016233  cmp     byte ptr [rcx+19h], 2
0x140016237  jb      loc_14001638A
0x14001623d  mov     edx, 9Bh
0x140016242  mov     r9d, [rdi+80h]
0x140016249  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016250  mov     rcx, [rcx+10h]
0x140016254  mov     dword ptr [rsp+130h+var_110], ebx
0x140016258  call    WPP_SF_Dd
0x14001625d  jmp     loc_14001638A
0x140016262  movups  xmm0, xmmword ptr [r14]
0x140016266  lea     rbx, [rdi+2A0h]
0x14001626d  mov     eax, 0FFFEh
0x140016272  movdqu  xmmword ptr [rbx], xmm0
0x140016276  add     [rbx], ax
0x140016279  test    cs:Microsoft_Windows_Storage_TieringEnableBits, 1
0x140016280  movzx   eax, word ptr [rbx]
0x140016283  jz      short loc_1400162D9
0x140016285  shr     ax, 1
0x140016288  lea     rdx, TIERENGINE_EVENT_MONITORING_VOLUME
0x14001628f  movzx   ecx, ax
0x140016292  mov     r9d, 3
0x140016298  lea     rax, [rsp+130h+var_100]
0x14001629d  mov     [rsp+130h+var_100], cx
0x1400162a2  mov     [rsp+130h+var_C8], rax
0x1400162a7  add     ecx, ecx
0x1400162a9  mov     rax, [rdi+2A8h]
0x1400162b0  mov     [rsp+78h], rax
0x1400162b5  lea     rax, [rsp+58h]
0x1400162ba  mov     [rsp+130h+var_110], rax
0x1400162bf  mov     [rsp+130h+var_C0], 2
0x1400162c8  mov     [rbp+30h+var_B0], ecx
0x1400162cb  mov     [rbp+30h+var_AC], 0
0x1400162d2  call    McGenEventWrite_EventWriteTransfer
0x1400162d7  jmp     short loc_1400162DB
0x1400162d9  xor     eax, eax
0x1400162db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400162e2  lea     rsi, WPP_GLOBAL_Control
0x1400162e9  cmp     rcx, rsi
0x1400162ec  jz      short loc_140016317
0x1400162ee  test    byte ptr [rcx+1Ch], 1
0x1400162f2  jz      short loc_140016317
0x1400162f4  cmp     byte ptr [rcx+19h], 4
0x1400162f8  jb      short loc_140016317
0x1400162fa  mov     rcx, [rcx+10h]
0x1400162fe  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016305  mov     edx, 9Ch
0x14001630a  mov     [rsp+130h+var_110], rbx
0x14001630f  mov     r9d, eax
0x140016312  call    WPP_SF_dZ
0x140016317  cmp     dword ptr [rdi+320h], 0FFFFFFFFh
0x14001631e  jnz     short loc_140016374
0x140016320  cmp     dword ptr [rdi+324h], 0FFFFFFFFh
0x140016327  jnz     short loc_140016374
0x140016329  mov     rdx, r14; struct _UNICODE_STRING *
0x14001632c  mov     rcx, rdi; this
0x14001632f  call    ?SetupJetFileNames@CTieredVolume@@AEAAJPEAU_UNICODE_STRING@@@Z; CTieredVolume::SetupJetFileNames(_UNICODE_STRING *)
0x140016334  mov     dword ptr [rsp+130h+var_F0], eax
0x140016338  mov     ebx, eax
0x14001633a  test    eax, eax
0x14001633c  jns     short loc_140016374
0x14001633e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016345  cmp     rcx, rsi
0x140016348  jz      short loc_14001638A
0x14001634a  test    byte ptr [rcx+1Ch], 1
0x14001634e  jz      short loc_14001638A
0x140016350  cmp     byte ptr [rcx+19h], 2
0x140016354  jb      short loc_14001638A
0x140016356  mov     rcx, [rcx+10h]
0x14001635a  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140016361  mov     edx, 9Dh
0x140016366  mov     dword ptr [rsp+130h+var_110], eax
0x14001636a  mov     r9, r14
0x14001636d  call    WPP_SF_Zd
0x140016372  jmp     short loc_14001638A
0x140016374  movups  xmm0, xmmword ptr [r14]
0x140016378  mov     dword ptr [rsp+130h+var_F0], 0
0x140016380  xor     ebx, ebx
0x140016382  movdqu  xmmword ptr [rdi+2B8h], xmm0
0x14001638a  lea     rcx, [rsp+130h+var_F8]; this
0x14001638f  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140016394  mov     eax, ebx
0x140016396  mov     rcx, [rbp+30h+var_50]
0x14001639a  xor     rcx, rsp; StackCookie
0x14001639d  call    __security_check_cookie
0x1400163a2  movaps  xmm6, [rsp+130h+var_48+8]
0x1400163aa  add     rsp, 108h
0x1400163b1  pop     r15
0x1400163b3  pop     r14
0x1400163b5  pop     rdi
0x1400163b6  pop     rsi
0x1400163b7  pop     rbx
0x1400163b8  pop     rbp
0x1400163b9  retn
```
