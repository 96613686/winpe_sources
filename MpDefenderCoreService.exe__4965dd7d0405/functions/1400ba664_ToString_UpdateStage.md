# ToString(UpdateStage)

- ea: `0x1400ba664`
- end: `0x1400ba7c6`
- name: `?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UpdateStage@@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400b8cfc`

## callees

- `0x14008d1fc`
- `0x1400ba664`

## string_xrefs

- `0x1400ba6ef`: `SEARCH_COMPLETED`
- `0x1400ba6bf`: `DOWNLOAD_COMPLETED`
- `0x1400ba6ad`: `INSTALL_STARTED`
- `0x1400ba725`: `INSTALL_PROGRESS`
- `0x1400ba79a`: `INSTALL_COMPLETED`
- `0x1400ba779`: `COMPLETED`
- `0x1400ba770`: `UPDATE_FAILED`
- `0x1400ba761`: `NO_UPDATE`

## pseudocode

```c
_QWORD *__fastcall ToString(_QWORD *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  unsigned __int64 v9; // r8
  const wchar_t *v10; // rdx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx

  if ( a2 > 8 )
  {
    v9 = 9;
    v11 = a2 - 9;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
        v9 = 15;
        v10 = L"REBOOT_REQUIRED";
        goto LABEL_32;
      }
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
          v10 = L"COMPLETED";
          goto LABEL_32;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          v9 = 13;
          v10 = L"UPDATE_FAILED";
          goto LABEL_32;
        }
        if ( v15 == 1 )
        {
          v10 = L"NO_UPDATE";
          goto LABEL_32;
        }
        goto LABEL_24;
      }
      v10 = L"REQUEST_PROCESSED";
    }
    else
    {
      v10 = L"INSTALL_COMPLETED";
    }
LABEL_31:
    v9 = 17;
    goto LABEL_32;
  }
  if ( a2 == 8 )
  {
    v9 = 16;
    v10 = L"INSTALL_PROGRESS";
    goto LABEL_32;
  }
  v3 = a2 - 1;
  if ( !v3 )
  {
    v9 = 5;
    v10 = L"START";
    goto LABEL_32;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v9 = 14;
    v10 = L"SEARCH_STARTED";
    goto LABEL_32;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v9 = 16;
    v10 = L"SEARCH_COMPLETED";
    goto LABEL_32;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v9 = 16;
    v10 = L"DOWNLOAD_STARTED";
    goto LABEL_32;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = L"DOWNLOAD_PROGRESS";
    goto LABEL_31;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v9 = 18;
    v10 = L"DOWNLOAD_COMPLETED";
    goto LABEL_32;
  }
  if ( v8 != 1 )
  {
LABEL_24:
    v9 = 7;
    v10 = L"Unknown";
    goto LABEL_32;
  }
  v9 = 15;
  v10 = L"INSTALL_STARTED";
LABEL_32:
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  std::wstring::_Construct<1,wchar_t const *>(a1, v10, v9);
  return a1;
}

```

## disassembly

```asm
0x1400ba664  push    rbx
0x1400ba666  sub     rsp, 30h
0x1400ba66a  mov     rbx, rcx
0x1400ba66d  xor     ecx, ecx
0x1400ba66f  cmp     edx, 8
0x1400ba672  jg      loc_1400BA72E
0x1400ba678  jz      loc_1400BA71F
0x1400ba67e  sub     edx, 1
0x1400ba681  jz      loc_1400BA70D
0x1400ba687  sub     edx, 1
0x1400ba68a  jz      short loc_1400BA6FB
0x1400ba68c  sub     edx, 1
0x1400ba68f  jz      short loc_1400BA6E9
0x1400ba691  sub     edx, 1
0x1400ba694  jz      short loc_1400BA6D7
0x1400ba696  sub     edx, 1
0x1400ba699  jz      short loc_1400BA6CB
0x1400ba69b  sub     edx, 1
0x1400ba69e  jz      short loc_1400BA6B9
0x1400ba6a0  cmp     edx, 1
0x1400ba6a3  jnz     loc_1400BA752
0x1400ba6a9  lea     r8d, [rcx+0Fh]
0x1400ba6ad  lea     rdx, aInstallStarted; "INSTALL_STARTED"
0x1400ba6b4  jmp     loc_1400BA7A7
0x1400ba6b9  mov     r8d, 12h
0x1400ba6bf  lea     rdx, aDownloadComple; "DOWNLOAD_COMPLETED"
0x1400ba6c6  jmp     loc_1400BA7A7
0x1400ba6cb  lea     rdx, aDownloadProgre; "DOWNLOAD_PROGRESS"
0x1400ba6d2  jmp     loc_1400BA7A1
0x1400ba6d7  mov     r8d, 10h
0x1400ba6dd  lea     rdx, aDownloadStarte; "DOWNLOAD_STARTED"
0x1400ba6e4  jmp     loc_1400BA7A7
0x1400ba6e9  mov     r8d, 10h
0x1400ba6ef  lea     rdx, aSearchComplete; "SEARCH_COMPLETED"
0x1400ba6f6  jmp     loc_1400BA7A7
0x1400ba6fb  mov     r8d, 0Eh
0x1400ba701  lea     rdx, aSearchStarted; "SEARCH_STARTED"
0x1400ba708  jmp     loc_1400BA7A7
0x1400ba70d  mov     r8d, 5
0x1400ba713  lea     rdx, aStart_1; "START"
0x1400ba71a  jmp     loc_1400BA7A7
0x1400ba71f  mov     r8d, 10h
0x1400ba725  lea     rdx, aInstallProgres; "INSTALL_PROGRESS"
0x1400ba72c  jmp     short loc_1400BA7A7
0x1400ba72e  mov     r8d, 9
0x1400ba734  sub     edx, r8d
0x1400ba737  jz      short loc_1400BA79A
0x1400ba739  sub     edx, 1
0x1400ba73c  jz      short loc_1400BA78B
0x1400ba73e  sub     edx, 1
0x1400ba741  jz      short loc_1400BA782
0x1400ba743  sub     edx, 1
0x1400ba746  jz      short loc_1400BA779
0x1400ba748  sub     edx, 1
0x1400ba74b  jz      short loc_1400BA76A
0x1400ba74d  cmp     edx, 1
0x1400ba750  jz      short loc_1400BA761
0x1400ba752  mov     r8d, 7
0x1400ba758  lea     rdx, aUnknown_2; "Unknown"
0x1400ba75f  jmp     short loc_1400BA7A7
0x1400ba761  lea     rdx, aNoUpdate; "NO_UPDATE"
0x1400ba768  jmp     short loc_1400BA7A7
0x1400ba76a  mov     r8d, 0Dh
0x1400ba770  lea     rdx, aUpdateFailed; "UPDATE_FAILED"
0x1400ba777  jmp     short loc_1400BA7A7
0x1400ba779  lea     rdx, aCompleted; "COMPLETED"
0x1400ba780  jmp     short loc_1400BA7A7
0x1400ba782  lea     rdx, aRequestProcess; "REQUEST_PROCESSED"
0x1400ba789  jmp     short loc_1400BA7A1
0x1400ba78b  mov     r8d, 0Fh
0x1400ba791  lea     rdx, aRebootRequired; "REBOOT_REQUIRED"
0x1400ba798  jmp     short loc_1400BA7A7
0x1400ba79a  lea     rdx, aInstallComplet; "INSTALL_COMPLETED"
0x1400ba7a1  mov     r8d, 11h
0x1400ba7a7  xorps   xmm0, xmm0
0x1400ba7aa  movups  xmmword ptr [rbx], xmm0
0x1400ba7ad  mov     [rbx+10h], rcx
0x1400ba7b1  mov     [rbx+18h], rcx
0x1400ba7b5  mov     rcx, rbx
0x1400ba7b8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400ba7bd  mov     rax, rbx
0x1400ba7c0  add     rsp, 30h
0x1400ba7c4  pop     rbx
0x1400ba7c5  retn
```
