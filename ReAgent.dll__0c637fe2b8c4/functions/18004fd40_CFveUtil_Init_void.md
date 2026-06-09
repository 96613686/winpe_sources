# CFveUtil::Init(void)

- ea: `0x18004fd40`
- end: `0x1800500a0`
- name: `?Init@CFveUtil@@AEAAKXZ`
- size: `864`
- prototype: `__int64 __fastcall(CFveUtil *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800502e0`

## callees

- `0x18004f8d0`
- `0x18004fd40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004fd63`
- `KERNEL32!GetLastError` at `0x18004fdae`
- `KERNEL32!GetLastError` at `0x18004fdfb`
- `KERNEL32!GetLastError` at `0x18004fe48`
- `KERNEL32!GetLastError` at `0x18004fe95`
- `KERNEL32!GetLastError` at `0x18004fee2`
- `KERNEL32!GetLastError` at `0x18004ff2f`
- `KERNEL32!GetLastError` at `0x18004ff7c`
- `KERNEL32!GetLastError` at `0x18004ffc9`
- `KERNEL32!GetLastError` at `0x180050016`
- `KERNEL32!GetLastError` at `0x18005005a`
- `KERNEL32!GetLastError` at `0x18004fd63`
- `KERNEL32!GetLastError` at `0x18004fdae`
- `KERNEL32!GetLastError` at `0x18004fdfb`
- `KERNEL32!GetLastError` at `0x18004fe48`
- `KERNEL32!GetLastError` at `0x18004fe95`
- `KERNEL32!GetLastError` at `0x18004fee2`
- `KERNEL32!GetLastError` at `0x18004ff2f`
- `KERNEL32!GetLastError` at `0x18004ff7c`
- `KERNEL32!GetLastError` at `0x18004ffc9`
- `KERNEL32!GetLastError` at `0x180050016`
- `KERNEL32!GetLastError` at `0x18005005a`
- `KERNEL32!GetProcAddress` at `0x18004fda0`
- `KERNEL32!GetProcAddress` at `0x18004fdec`
- `KERNEL32!GetProcAddress` at `0x18004fe39`
- `KERNEL32!GetProcAddress` at `0x18004fe86`
- `KERNEL32!GetProcAddress` at `0x18004fed3`
- `KERNEL32!GetProcAddress` at `0x18004ff20`
- `KERNEL32!GetProcAddress` at `0x18004ff6d`
- `KERNEL32!GetProcAddress` at `0x18004ffba`
- `KERNEL32!GetProcAddress` at `0x180050007`
- `KERNEL32!GetProcAddress` at `0x18005004b`
- `KERNEL32!GetProcAddress` at `0x18004fda0`
- `KERNEL32!GetProcAddress` at `0x18004fdec`
- `KERNEL32!GetProcAddress` at `0x18004fe39`
- `KERNEL32!GetProcAddress` at `0x18004fe86`
- `KERNEL32!GetProcAddress` at `0x18004fed3`
- `KERNEL32!GetProcAddress` at `0x18004ff20`
- `KERNEL32!GetProcAddress` at `0x18004ff6d`
- `KERNEL32!GetProcAddress` at `0x18004ffba`
- `KERNEL32!GetProcAddress` at `0x180050007`
- `KERNEL32!GetProcAddress` at `0x18005004b`
- `KERNEL32!LoadLibraryW` at `0x18004fd54`
- `KERNEL32!LoadLibraryW` at `0x18004fd54`

## string_xrefs

- `0x18004fe32`: `FveEnableRawAccessW`
- `0x18004fe7f`: `FveOpenVolumeW`
- `0x18004fecc`: `FveOpenVolumeByHandle`
- `0x18004ff66`: `FveCommitChanges`

## pseudocode

```c
__int64 __fastcall CFveUtil::Init(CFveUtil *this)
{
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  DWORD v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax

  LibraryW = LoadLibraryW(L"fveapi");
  *((_QWORD *)this + 10) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "FveGetStatusW");
    *(_QWORD *)this = ProcAddress;
    if ( ProcAddress )
    {
      v8 = GetProcAddress(*((HMODULE *)this + 10), "FveGetStatus");
      *((_QWORD *)this + 1) = v8;
      if ( v8 )
      {
        v9 = GetProcAddress(*((HMODULE *)this + 10), "FveEnableRawAccessW");
        *((_QWORD *)this + 2) = v9;
        if ( v9 )
        {
          v10 = GetProcAddress(*((HMODULE *)this + 10), "FveOpenVolumeW");
          *((_QWORD *)this + 3) = v10;
          if ( v10 )
          {
            v11 = GetProcAddress(*((HMODULE *)this + 10), "FveOpenVolumeByHandle");
            *((_QWORD *)this + 4) = v11;
            if ( v11 )
            {
              v12 = GetProcAddress(*((HMODULE *)this + 10), "FveKeyManagement");
              *((_QWORD *)this + 5) = v12;
              if ( v12 )
              {
                v13 = GetProcAddress(*((HMODULE *)this + 10), "FveCommitChanges");
                *((_QWORD *)this + 6) = v13;
                if ( v13 )
                {
                  v14 = GetProcAddress(*((HMODULE *)this + 10), "FveCloseVolume");
                  *((_QWORD *)this + 7) = v14;
                  if ( v14 )
                  {
                    v15 = GetProcAddress(*((HMODULE *)this + 10), "FveLockVolume");
                    *((_QWORD *)this + 8) = v15;
                    if ( v15 )
                    {
                      v4 = 0;
                      v16 = GetProcAddress(*((HMODULE *)this + 10), "FveControl");
                      *((_QWORD *)this + 9) = v16;
                      if ( !v16 )
                      {
                        LastError = GetLastError();
                        v4 = LastError;
                        v5 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v6 = 20;
                          goto LABEL_45;
                        }
                      }
                    }
                    else
                    {
                      LastError = GetLastError();
                      v4 = LastError;
                      v5 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        v6 = 19;
                        goto LABEL_45;
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    v4 = LastError;
                    v5 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v6 = 18;
                      goto LABEL_45;
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v4 = LastError;
                  v5 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v6 = 17;
                    goto LABEL_45;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v4 = LastError;
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v6 = 16;
                  goto LABEL_45;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v6 = 15;
                goto LABEL_45;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v6 = 14;
              goto LABEL_45;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v6 = 13;
            goto LABEL_45;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v6 = 12;
          goto LABEL_45;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 11;
        goto LABEL_45;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 10;
LABEL_45:
      WPP_SF_d(v5[2], v6, WPP_9524a493ea453572c3fd8a18ab1bebb5_Traceguids, LastError);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004fd40  mov     [rsp+arg_0], rbx
0x18004fd45  push    rdi
0x18004fd46  sub     rsp, 20h
0x18004fd4a  mov     rdi, rcx
0x18004fd4d  lea     rcx, aFveapi; "fveapi"
0x18004fd54  call    cs:__imp_LoadLibraryW
0x18004fd5a  mov     [rdi+50h], rax
0x18004fd5e  test    rax, rax
0x18004fd61  jnz     short loc_18004FD96
0x18004fd63  call    cs:__imp_GetLastError
0x18004fd69  mov     ebx, eax
0x18004fd6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd72  lea     rdx, WPP_GLOBAL_Control
0x18004fd79  cmp     rcx, rdx
0x18004fd7c  jz      loc_180050093
0x18004fd82  test    byte ptr [rcx+1Ch], 2
0x18004fd86  jz      loc_180050093
0x18004fd8c  mov     edx, 0Ah
0x18004fd91  jmp     loc_180050080
0x18004fd96  lea     rdx, aFvegetstatusw; "FveGetStatusW"
0x18004fd9d  mov     rcx, rax; hModule
0x18004fda0  call    cs:__imp_GetProcAddress
0x18004fda6  mov     [rdi], rax
0x18004fda9  test    rax, rax
0x18004fdac  jnz     short loc_18004FDE1
0x18004fdae  call    cs:__imp_GetLastError
0x18004fdb4  mov     ebx, eax
0x18004fdb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fdbd  lea     rdx, WPP_GLOBAL_Control
0x18004fdc4  cmp     rcx, rdx
0x18004fdc7  jz      loc_180050093
0x18004fdcd  test    byte ptr [rcx+1Ch], 2
0x18004fdd1  jz      loc_180050093
0x18004fdd7  mov     edx, 0Bh
0x18004fddc  jmp     loc_180050080
0x18004fde1  mov     rcx, [rdi+50h]; hModule
0x18004fde5  lea     rdx, aFvegetstatus; "FveGetStatus"
0x18004fdec  call    cs:__imp_GetProcAddress
0x18004fdf2  mov     [rdi+8], rax
0x18004fdf6  test    rax, rax
0x18004fdf9  jnz     short loc_18004FE2E
0x18004fdfb  call    cs:__imp_GetLastError
0x18004fe01  mov     ebx, eax
0x18004fe03  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fe0a  lea     rdx, WPP_GLOBAL_Control
0x18004fe11  cmp     rcx, rdx
0x18004fe14  jz      loc_180050093
0x18004fe1a  test    byte ptr [rcx+1Ch], 2
0x18004fe1e  jz      loc_180050093
0x18004fe24  mov     edx, 0Ch
0x18004fe29  jmp     loc_180050080
0x18004fe2e  mov     rcx, [rdi+50h]; hModule
0x18004fe32  lea     rdx, aFveenablerawac; "FveEnableRawAccessW"
0x18004fe39  call    cs:__imp_GetProcAddress
0x18004fe3f  mov     [rdi+10h], rax
0x18004fe43  test    rax, rax
0x18004fe46  jnz     short loc_18004FE7B
0x18004fe48  call    cs:__imp_GetLastError
0x18004fe4e  mov     ebx, eax
0x18004fe50  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fe57  lea     rdx, WPP_GLOBAL_Control
0x18004fe5e  cmp     rcx, rdx
0x18004fe61  jz      loc_180050093
0x18004fe67  test    byte ptr [rcx+1Ch], 2
0x18004fe6b  jz      loc_180050093
0x18004fe71  mov     edx, 0Dh
0x18004fe76  jmp     loc_180050080
0x18004fe7b  mov     rcx, [rdi+50h]; hModule
0x18004fe7f  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x18004fe86  call    cs:__imp_GetProcAddress
0x18004fe8c  mov     [rdi+18h], rax
0x18004fe90  test    rax, rax
0x18004fe93  jnz     short loc_18004FEC8
0x18004fe95  call    cs:__imp_GetLastError
0x18004fe9b  mov     ebx, eax
0x18004fe9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fea4  lea     rdx, WPP_GLOBAL_Control
0x18004feab  cmp     rcx, rdx
0x18004feae  jz      loc_180050093
0x18004feb4  test    byte ptr [rcx+1Ch], 2
0x18004feb8  jz      loc_180050093
0x18004febe  mov     edx, 0Eh
0x18004fec3  jmp     loc_180050080
0x18004fec8  mov     rcx, [rdi+50h]; hModule
0x18004fecc  lea     rdx, aFveopenvolumeb; "FveOpenVolumeByHandle"
0x18004fed3  call    cs:__imp_GetProcAddress
0x18004fed9  mov     [rdi+20h], rax
0x18004fedd  test    rax, rax
0x18004fee0  jnz     short loc_18004FF15
0x18004fee2  call    cs:__imp_GetLastError
0x18004fee8  mov     ebx, eax
0x18004feea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fef1  lea     rdx, WPP_GLOBAL_Control
0x18004fef8  cmp     rcx, rdx
0x18004fefb  jz      loc_180050093
0x18004ff01  test    byte ptr [rcx+1Ch], 2
0x18004ff05  jz      loc_180050093
0x18004ff0b  mov     edx, 0Fh
0x18004ff10  jmp     loc_180050080
0x18004ff15  mov     rcx, [rdi+50h]; hModule
0x18004ff19  lea     rdx, aFvekeymanageme; "FveKeyManagement"
0x18004ff20  call    cs:__imp_GetProcAddress
0x18004ff26  mov     [rdi+28h], rax
0x18004ff2a  test    rax, rax
0x18004ff2d  jnz     short loc_18004FF62
0x18004ff2f  call    cs:__imp_GetLastError
0x18004ff35  mov     ebx, eax
0x18004ff37  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ff3e  lea     rdx, WPP_GLOBAL_Control
0x18004ff45  cmp     rcx, rdx
0x18004ff48  jz      loc_180050093
0x18004ff4e  test    byte ptr [rcx+1Ch], 2
0x18004ff52  jz      loc_180050093
0x18004ff58  mov     edx, 10h
0x18004ff5d  jmp     loc_180050080
0x18004ff62  mov     rcx, [rdi+50h]; hModule
0x18004ff66  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x18004ff6d  call    cs:__imp_GetProcAddress
0x18004ff73  mov     [rdi+30h], rax
0x18004ff77  test    rax, rax
0x18004ff7a  jnz     short loc_18004FFAF
0x18004ff7c  call    cs:__imp_GetLastError
0x18004ff82  mov     ebx, eax
0x18004ff84  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ff8b  lea     rdx, WPP_GLOBAL_Control
0x18004ff92  cmp     rcx, rdx
0x18004ff95  jz      loc_180050093
0x18004ff9b  test    byte ptr [rcx+1Ch], 2
0x18004ff9f  jz      loc_180050093
0x18004ffa5  mov     edx, 11h
0x18004ffaa  jmp     loc_180050080
0x18004ffaf  mov     rcx, [rdi+50h]; hModule
0x18004ffb3  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18004ffba  call    cs:__imp_GetProcAddress
0x18004ffc0  mov     [rdi+38h], rax
0x18004ffc4  test    rax, rax
0x18004ffc7  jnz     short loc_18004FFFC
0x18004ffc9  call    cs:__imp_GetLastError
0x18004ffcf  mov     ebx, eax
0x18004ffd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ffd8  lea     rdx, WPP_GLOBAL_Control
0x18004ffdf  cmp     rcx, rdx
0x18004ffe2  jz      loc_180050093
0x18004ffe8  test    byte ptr [rcx+1Ch], 2
0x18004ffec  jz      loc_180050093
0x18004fff2  mov     edx, 12h
0x18004fff7  jmp     loc_180050080
0x18004fffc  mov     rcx, [rdi+50h]; hModule
0x180050000  lea     rdx, aFvelockvolume; "FveLockVolume"
0x180050007  call    cs:__imp_GetProcAddress
0x18005000d  mov     [rdi+40h], rax
0x180050011  test    rax, rax
0x180050014  jnz     short loc_18005003E
0x180050016  call    cs:__imp_GetLastError
0x18005001c  mov     ebx, eax
0x18005001e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050025  lea     rdx, WPP_GLOBAL_Control
0x18005002c  cmp     rcx, rdx
0x18005002f  jz      short loc_180050093
0x180050031  test    byte ptr [rcx+1Ch], 2
0x180050035  jz      short loc_180050093
0x180050037  mov     edx, 13h
0x18005003c  jmp     short loc_180050080
0x18005003e  mov     rcx, [rdi+50h]; hModule
0x180050042  lea     rdx, aFvecontrol; "FveControl"
0x180050049  xor     ebx, ebx
0x18005004b  call    cs:__imp_GetProcAddress
0x180050051  mov     [rdi+48h], rax
0x180050055  test    rax, rax
0x180050058  jnz     short loc_180050093
0x18005005a  call    cs:__imp_GetLastError
0x180050060  mov     ebx, eax
0x180050062  mov     rcx, cs:WPP_GLOBAL_Control
0x180050069  lea     rdx, WPP_GLOBAL_Control
0x180050070  cmp     rcx, rdx
0x180050073  jz      short loc_180050093
0x180050075  test    byte ptr [rcx+1Ch], 2
0x180050079  jz      short loc_180050093
0x18005007b  mov     edx, 14h
0x180050080  mov     rcx, [rcx+10h]
0x180050084  lea     r8, WPP_9524a493ea453572c3fd8a18ab1bebb5_Traceguids
0x18005008b  mov     r9d, eax
0x18005008e  call    WPP_SF_d
0x180050093  mov     eax, ebx
0x180050095  mov     rbx, [rsp+28h+arg_0]
0x18005009a  add     rsp, 20h
0x18005009e  pop     rdi
0x18005009f  retn
```
