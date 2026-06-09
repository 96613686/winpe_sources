# CMbrDisk::WriteBootSectorCode(_PARTITION_INFORMATION_EX *,int)

- ea: `0x180057830`
- end: `0x180057b8c`
- name: `?WriteBootSectorCode@CMbrDisk@@UEAAKPEAU_PARTITION_INFORMATION_EX@@H@Z`
- size: `860`
- prototype: `unsigned int __fastcall(CMbrDisk *__hidden this, struct _PARTITION_INFORMATION_EX *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x18000c6c0`
- `0x18000c6f0`
- `0x18004d52c`
- `0x18004e4f0`
- `0x18004f8d0`
- `0x18004fb04`
- `0x18004fc28`
- `0x180054c34`
- `0x180057830`
- `0x180057b94`
- `0x180057de8`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180057a85`
- `KERNEL32!GetLastError` at `0x180057a85`
- `KERNEL32!CreateFileW` at `0x180057a76`
- `KERNEL32!CreateFileW` at `0x180057a76`
- `KERNEL32!CloseHandle` at `0x180057b5d`
- `KERNEL32!CloseHandle` at `0x180057b5d`

## pseudocode

```c
__int64 __fastcall CMbrDisk::WriteBootSectorCode(CMbrDisk *this, struct _PARTITION_INFORMATION_EX *a2, int a3)
{
  unsigned int v7; // ebx
  unsigned int PartitionName; // eax
  int v9; // eax
  _UNKNOWN **v10; // rcx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  DWORD DoesPathExist; // eax
  HANDLE FileW; // rax
  int v15; // edx
  void *v16; // r14
  DWORD LastError; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned __int64 v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v22[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(v22, 0, 0x208u);
  if ( !a2 )
    return 87;
  v7 = 0;
  if ( a2->Mbr.BootIndicator )
  {
    PartitionName = CDisk::GetPartitionName(this, a2->PartitionNumber, FileName, 0x104u, 0);
    v7 = PartitionName;
    if ( PartitionName )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          274,
          &WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids,
          PartitionName);
      return v7;
    }
    if ( a3 )
    {
LABEL_30:
      FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0xA0000000, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v16 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            277,
            (unsigned int)&WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids,
            (unsigned int)FileName,
            LastError);
        return v7;
      }
      v18 = Utils::LockUnlockVolume(FileW, v15);
      if ( v18
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          278,
          (unsigned int)&WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids,
          (unsigned int)FileName,
          v18);
      }
      if ( (*(unsigned int (__fastcall **)(CMbrDisk *, struct _PARTITION_INFORMATION_EX *))(*(_QWORD *)this + 40LL))(
             this,
             a2) )
      {
        v19 = CMbrDisk::WriteBootSectorCodeNtfs(this, a2, v16);
      }
      else
      {
        if ( !(*(unsigned int (__fastcall **)(CMbrDisk *, struct _PARTITION_INFORMATION_EX *))(*(_QWORD *)this + 48LL))(
                this,
                a2) )
        {
          v7 = 1005;
LABEL_44:
          if ( v16 )
            CloseHandle(v16);
          return v7;
        }
        v19 = CMbrDisk::WriteBootSectorCodeFat32(this, a2, v16);
      }
      v7 = v19;
      goto LABEL_44;
    }
    v20[0] = 0;
    v9 = StringCchLengthW(FileName, 0x7FFFFFFFu, v20);
    LOWORD(v7) = v9;
    if ( v9 >= 0 )
    {
      if ( !v20[0] || (v12 = L"%s\\%s", *((_WORD *)&v20[1] + v20[0] + 3) == 92) )
        v12 = L"%s%s";
      v9 = StringCchPrintfW(v22, 0x104u, v12, FileName, L"BootMgr");
      LOWORD(v7) = v9;
      if ( v9 >= 0 )
      {
LABEL_25:
        DoesPathExist = Utils::DoesPathExist(v22);
        if ( DoesPathExist )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              276,
              &WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids,
              DoesPathExist);
          return 0;
        }
        goto LABEL_30;
      }
      v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 15;
        goto LABEL_20;
      }
    }
    else
    {
      v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 14;
LABEL_20:
        WPP_SF_d(v10[2], v11, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v9);
        v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
    }
    v7 = (unsigned __int16)v7;
    if ( (_WORD)v7 )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
        WPP_SF_SSD((TRACEHANDLE)v10[2], (__int64)L"BootMgr", v7);
      return v7;
    }
    goto LABEL_25;
  }
  return v7;
}

```

## disassembly

```asm
0x180057830  mov     [rsp-8+arg_10], rbx
0x180057835  push    rbp
0x180057836  push    rsi
0x180057837  push    r12
0x180057839  push    r14
0x18005783b  push    r15
0x18005783d  lea     rbp, [rsp-380h]
0x180057845  sub     rsp, 480h
0x18005784c  mov     rax, cs:__security_cookie
0x180057853  xor     rax, rsp
0x180057856  mov     [rbp+3A0h+var_30], rax
0x18005785d  mov     r14d, r8d
0x180057860  mov     r15, rdx
0x180057863  mov     r12, rcx
0x180057866  mov     ebx, 208h
0x18005786b  mov     r8d, ebx; Size
0x18005786e  lea     rcx, [rsp+4A0h+FileName]; void *
0x180057873  xor     edx, edx; Val
0x180057875  call    memset_0
0x18005787a  mov     r8d, ebx; Size
0x18005787d  lea     rcx, [rbp+3A0h+var_240]; void *
0x180057884  xor     edx, edx; Val
0x180057886  call    memset_0
0x18005788b  test    r15, r15
0x18005788e  jnz     short loc_180057899
0x180057890  lea     eax, [r15+57h]
0x180057894  jmp     loc_180057B65
0x180057899  xor     ebx, ebx
0x18005789b  cmp     [r15+21h], bl
0x18005789f  jz      loc_180057B63
0x1800578a5  mov     edx, [r15+18h]; unsigned int
0x1800578a9  lea     r8, [rsp+4A0h+FileName]; unsigned __int16 *
0x1800578ae  mov     r9d, 104h; unsigned int
0x1800578b4  mov     [rsp+4A0h+dwCreationDisposition], ebx; int
0x1800578b8  mov     rcx, r12; this
0x1800578bb  call    ?GetPartitionName@CDisk@@QEAAKKPEAGKH@Z; CDisk::GetPartitionName(ulong,ushort *,ulong,int)
0x1800578c0  mov     ebx, eax
0x1800578c2  test    eax, eax
0x1800578c4  jz      short loc_180057904
0x1800578c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578cd  lea     rsi, WPP_GLOBAL_Control
0x1800578d4  cmp     rcx, rsi
0x1800578d7  jz      loc_180057B63
0x1800578dd  test    byte ptr [rcx+1Ch], 2
0x1800578e1  jz      loc_180057B63
0x1800578e7  mov     rcx, [rcx+10h]
0x1800578eb  lea     r8, WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids
0x1800578f2  mov     edx, 112h
0x1800578f7  mov     r9d, eax
0x1800578fa  call    WPP_SF_d
0x1800578ff  jmp     loc_180057B63
0x180057904  lea     rsi, WPP_GLOBAL_Control
0x18005790b  test    r14d, r14d
0x18005790e  jnz     loc_180057A4C
0x180057914  lea     r8, [rsp+4A0h+var_460]; unsigned __int64 *
0x180057919  mov     [rsp+4A0h+var_460], 0
0x180057922  mov     edx, 7FFFFFFFh; unsigned __int64
0x180057927  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18005792c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180057931  lea     r14, aBootmgr; "BootMgr"
0x180057938  mov     ebx, eax
0x18005793a  test    eax, eax
0x18005793c  jns     short loc_180057957
0x18005793e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057945  cmp     rcx, rsi
0x180057948  jz      short loc_1800579C9
0x18005794a  test    byte ptr [rcx+1Ch], 2
0x18005794e  jz      short loc_1800579C9
0x180057950  mov     edx, 0Eh
0x180057955  jmp     short loc_1800579AF
0x180057957  mov     rax, [rsp+4A0h+var_460]
0x18005795c  test    rax, rax
0x18005795f  jz      short loc_180057970
0x180057961  cmp     [rsp+rax*2+4A0h+var_452], 5Ch ; '\'
0x180057967  lea     r8, aSS_1; "%s\\%s"
0x18005796e  jnz     short loc_180057977
0x180057970  lea     r8, aSS_2; "%s%s"
0x180057977  lea     r9, [rsp+4A0h+FileName]
0x18005797c  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x180057981  mov     edx, 104h; unsigned __int64
0x180057986  lea     rcx, [rbp+3A0h+var_240]; unsigned __int16 *
0x18005798d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057992  mov     ebx, eax
0x180057994  test    eax, eax
0x180057996  jns     short loc_180057A0B
0x180057998  mov     rcx, cs:WPP_GLOBAL_Control
0x18005799f  cmp     rcx, rsi
0x1800579a2  jz      short loc_1800579C9
0x1800579a4  test    byte ptr [rcx+1Ch], 2
0x1800579a8  jz      short loc_1800579C9
0x1800579aa  mov     edx, 0Fh
0x1800579af  mov     rcx, [rcx+10h]
0x1800579b3  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x1800579ba  mov     r9d, eax
0x1800579bd  call    WPP_SF_d
0x1800579c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579c9  movzx   ebx, bx
0x1800579cc  test    ebx, ebx
0x1800579ce  jz      short loc_180057A0B
0x1800579d0  cmp     rcx, rsi
0x1800579d3  jz      loc_180057B63
0x1800579d9  test    byte ptr [rcx+1Ch], 2
0x1800579dd  jz      loc_180057B63
0x1800579e3  mov     rcx, [rcx+10h]; LoggerHandle
0x1800579e7  lea     r9, [rsp+4A0h+FileName]
0x1800579ec  mov     edx, 113h
0x1800579f1  mov     [rsp+4A0h+dwFlagsAndAttributes], ebx; char
0x1800579f5  lea     r8, WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids
0x1800579fc  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14; __int64
0x180057a01  call    WPP_SF_SSD
0x180057a06  jmp     loc_180057B63
0x180057a0b  lea     rcx, [rbp+3A0h+var_240]; unsigned __int16 *
0x180057a12  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180057a17  test    eax, eax
0x180057a19  jz      short loc_180057A4C
0x180057a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a22  cmp     rcx, rsi
0x180057a25  jz      short loc_180057A45
0x180057a27  test    byte ptr [rcx+1Ch], 2
0x180057a2b  jz      short loc_180057A45
0x180057a2d  mov     rcx, [rcx+10h]
0x180057a31  lea     r8, WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids
0x180057a38  mov     edx, 114h
0x180057a3d  mov     r9d, eax
0x180057a40  call    WPP_SF_d
0x180057a45  xor     ebx, ebx
0x180057a47  jmp     loc_180057B63
0x180057a4c  xor     r9d, r9d; lpSecurityAttributes
0x180057a4f  mov     [rsp+4A0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180057a58  mov     [rsp+4A0h+dwFlagsAndAttributes], 0A0000000h; dwFlagsAndAttributes
0x180057a60  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180057a65  mov     edx, 0C0000000h; dwDesiredAccess
0x180057a6a  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180057a72  lea     r8d, [r9+7]; dwShareMode
0x180057a76  call    cs:__imp_CreateFileW
0x180057a7c  mov     r14, rax
0x180057a7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180057a83  jnz     short loc_180057ACA
0x180057a85  call    cs:__imp_GetLastError
0x180057a8b  mov     ebx, eax
0x180057a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a94  cmp     rcx, rsi
0x180057a97  jz      loc_180057B63
0x180057a9d  test    byte ptr [rcx+1Ch], 2
0x180057aa1  jz      loc_180057B63
0x180057aa7  mov     rcx, [rcx+10h]
0x180057aab  lea     r9, [rsp+4A0h+FileName]
0x180057ab0  mov     edx, 115h
0x180057ab5  mov     [rsp+4A0h+dwCreationDisposition], eax
0x180057ab9  lea     r8, WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids
0x180057ac0  call    WPP_SF_Sd
0x180057ac5  jmp     loc_180057B63
0x180057aca  mov     rcx, r14; void *
0x180057acd  call    ?LockUnlockVolume@Utils@@SAKPEAXH@Z; Utils::LockUnlockVolume(void *,int)
0x180057ad2  test    eax, eax
0x180057ad4  jz      short loc_180057B06
0x180057ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180057add  cmp     rcx, rsi
0x180057ae0  jz      short loc_180057B06
0x180057ae2  test    byte ptr [rcx+1Ch], 2
0x180057ae6  jz      short loc_180057B06
0x180057ae8  mov     rcx, [rcx+10h]
0x180057aec  lea     r9, [rsp+4A0h+FileName]
0x180057af1  mov     edx, 116h
0x180057af6  mov     [rsp+4A0h+dwCreationDisposition], eax
0x180057afa  lea     r8, WPP_f6c43db1db6a306f0794b532afe57ecb_Traceguids
0x180057b01  call    WPP_SF_Sd
0x180057b06  mov     rax, [r12]
0x180057b0a  mov     rdx, r15
0x180057b0d  mov     rcx, r12
0x180057b10  mov     rax, [rax+28h]
0x180057b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b19  mov     rdx, r15; struct _PARTITION_INFORMATION_EX *
0x180057b1c  mov     rcx, r12; this
0x180057b1f  test    eax, eax
0x180057b21  jz      short loc_180057B2D
0x180057b23  mov     r8, r14; void *
0x180057b26  call    ?WriteBootSectorCodeNtfs@CMbrDisk@@AEAAKPEAU_PARTITION_INFORMATION_EX@@PEAX@Z; CMbrDisk::WriteBootSectorCodeNtfs(_PARTITION_INFORMATION_EX *,void *)
0x180057b2b  jmp     short loc_180057B4C
0x180057b2d  mov     rax, [r12]
0x180057b31  mov     rax, [rax+30h]
0x180057b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b3a  test    eax, eax
0x180057b3c  jz      short loc_180057B50
0x180057b3e  mov     r8, r14; void *
0x180057b41  mov     rdx, r15; struct _PARTITION_INFORMATION_EX *
0x180057b44  mov     rcx, r12; this
0x180057b47  call    ?WriteBootSectorCodeFat32@CMbrDisk@@AEAAKPEAU_PARTITION_INFORMATION_EX@@PEAX@Z; CMbrDisk::WriteBootSectorCodeFat32(_PARTITION_INFORMATION_EX *,void *)
0x180057b4c  mov     ebx, eax
0x180057b4e  jmp     short loc_180057B55
0x180057b50  mov     ebx, 3EDh
0x180057b55  test    r14, r14
0x180057b58  jz      short loc_180057B63
0x180057b5a  mov     rcx, r14; hObject
0x180057b5d  call    cs:__imp_CloseHandle
0x180057b63  mov     eax, ebx
0x180057b65  mov     rcx, [rbp+3A0h+var_30]
0x180057b6c  xor     rcx, rsp; StackCookie
0x180057b6f  call    __security_check_cookie
0x180057b74  mov     rbx, [rsp+4A0h+arg_10]
0x180057b7c  add     rsp, 480h
0x180057b83  pop     r15
0x180057b85  pop     r14
0x180057b87  pop     r12
0x180057b89  pop     rsi
0x180057b8a  pop     rbp
0x180057b8b  retn
```
