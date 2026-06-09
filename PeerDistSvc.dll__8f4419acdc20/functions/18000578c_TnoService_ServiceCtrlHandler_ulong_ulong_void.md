# TnoService::ServiceCtrlHandler(ulong,ulong,void *)

- ea: `0x18000578c`
- end: `0x180005943`
- name: `?ServiceCtrlHandler@TnoService@@QEAAKKKPEAX@Z`
- size: `439`
- prototype: `unsigned int __fastcall(TnoService *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180005770`

## callees

- `0x180004374`
- `0x180005604`
- `0x18000578c`
- `0x180008290`
- `0x180008360`
- `0x1800190f0`
- `0x180159010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800058e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800058e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ea`

## pseudocode

```c
__int64 __fastcall TnoService::ServiceCtrlHandler(SERVICE_STATUS_HANDLE *this, int a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v4; // r15d
  int v8; // edx
  int v9; // edx
  int v10; // edx
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ebp
  __int64 v14; // rcx
  const char *v15; // r9
  SERVICE_STATUS_HANDLE v16; // rcx
  SERVICE_STATUS_HANDLE v17; // rcx
  struct _SERVICE_STATUS *v19; // rdx
  SERVICE_STATUS_HANDLE v20; // rcx
  DWORD LastError; // eax

  v4 = 0;
  v8 = a2 - 1;
  if ( v8 )
  {
    v9 = v8 - 3;
    if ( !v9 )
      return v4;
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 8 )
      {
        if ( a3 == 32787 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 155, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          if ( a4 )
          {
            v12 = *a4 - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
            if ( *a4 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
              v12 = a4[1] - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
            if ( !v12 && *((_DWORD *)a4 + 4) == 4 )
            {
              v13 = *((_DWORD *)a4 + 5);
              if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)v11 + 27) & 0x800) != 0
                && *((_BYTE *)v11 + 105) >= 3u )
              {
                v14 = *((_QWORD *)v11 + 12);
                v15 = "exited";
                if ( v13 )
                  v15 = "entered";
                WPP_SF_s(v14, 156, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v15);
              }
              TnoService::NetworkQuietModeEvent((TnoService *)this, v13);
            }
          }
        }
        else
        {
          v16 = this[51];
          if ( v16 )
            (*(void (__fastcall **)(SERVICE_STATUS_HANDLE, _QWORD))(*(_QWORD *)v16 + 32LL))(v16, a3);
          v17 = this[33];
          if ( v17 )
            (*(void (__fastcall **)(SERVICE_STATUS_HANDLE, _QWORD))(*(_QWORD *)v17 + 80LL))(v17, a3);
        }
      }
      else
      {
        return 120;
      }
      return v4;
    }
  }
  v19 = (struct _SERVICE_STATUS *)(this + 7);
  *((_DWORD *)this + 16) = 0;
  v20 = this[6];
  v19->dwCurrentState = 3;
  if ( !SetServiceStatus(v20, v19) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 157, WPP_09eff81643953ecc218449769581d5a4_Traceguids, LastError);
    }
  }
  Event::Set((Event *)(this + 12));
  return 0;
}

```

## disassembly

```asm
0x18000578c  push    rbx
0x18000578e  push    rbp
0x18000578f  push    rsi
0x180005790  push    rdi
0x180005791  push    r14
0x180005793  push    r15
0x180005795  sub     rsp, 28h
0x180005799  xor     r15d, r15d
0x18000579c  mov     r14, r9
0x18000579f  mov     edi, r8d
0x1800057a2  mov     rbx, rcx
0x1800057a5  sub     edx, 1
0x1800057a8  jz      loc_1800058CD
0x1800057ae  sub     edx, 3
0x1800057b1  jz      loc_1800058C8
0x1800057b7  sub     edx, 1
0x1800057ba  jz      loc_1800058CD
0x1800057c0  cmp     edx, 8
0x1800057c3  jz      short loc_1800057D0
0x1800057c5  mov     r15d, 78h ; 'x'
0x1800057cb  jmp     loc_1800058C8
0x1800057d0  cmp     edi, 8013h
0x1800057d6  jnz     loc_180005894
0x1800057dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057e3  lea     rsi, WPP_GLOBAL_Control
0x1800057ea  mov     edi, 800h
0x1800057ef  cmp     rcx, rsi
0x1800057f2  jz      short loc_18000581B
0x1800057f4  test    [rcx+6Ch], edi
0x1800057f7  jz      short loc_18000581B
0x1800057f9  cmp     byte ptr [rcx+69h], 3
0x1800057fd  jb      short loc_18000581B
0x1800057ff  mov     rcx, [rcx+60h]
0x180005803  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x18000580a  mov     edx, 9Bh
0x18000580f  call    WPP_SF_
0x180005814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000581b  test    r14, r14
0x18000581e  jz      loc_1800058C8
0x180005824  mov     rax, [r14]
0x180005827  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18000582e  jnz     short loc_18000583B
0x180005830  mov     rax, [r14+8]
0x180005834  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18000583b  test    rax, rax
0x18000583e  jnz     loc_1800058C8
0x180005844  cmp     dword ptr [r14+10h], 4
0x180005849  jnz     short loc_1800058C8
0x18000584b  mov     ebp, [r14+14h]
0x18000584f  cmp     rcx, rsi
0x180005852  jz      short loc_180005888
0x180005854  test    [rcx+6Ch], edi
0x180005857  jz      short loc_180005888
0x180005859  cmp     byte ptr [rcx+69h], 3
0x18000585d  jb      short loc_180005888
0x18000585f  mov     rcx, [rcx+60h]
0x180005863  lea     rax, aEntered; "entered"
0x18000586a  test    ebp, ebp
0x18000586c  lea     r9, aExited; "exited"
0x180005873  mov     edx, 9Ch
0x180005878  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x18000587f  cmovnz  r9, rax
0x180005883  call    WPP_SF_s
0x180005888  mov     edx, ebp; unsigned int
0x18000588a  mov     rcx, rbx; this
0x18000588d  call    ?NetworkQuietModeEvent@TnoService@@QEAAXK@Z; TnoService::NetworkQuietModeEvent(ulong)
0x180005892  jmp     short loc_1800058C8
0x180005894  mov     rcx, [rcx+198h]
0x18000589b  test    rcx, rcx
0x18000589e  jz      short loc_1800058AE
0x1800058a0  mov     rax, [rcx]
0x1800058a3  mov     edx, edi
0x1800058a5  mov     rax, [rax+20h]
0x1800058a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ae  mov     rcx, [rbx+108h]
0x1800058b5  test    rcx, rcx
0x1800058b8  jz      short loc_1800058C8
0x1800058ba  mov     rdx, [rcx]
0x1800058bd  mov     rax, [rdx+50h]
0x1800058c1  mov     edx, edi
0x1800058c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c8  mov     eax, r15d
0x1800058cb  jmp     short loc_180005936
0x1800058cd  lea     rdx, [rcx+38h]; lpServiceStatus
0x1800058d1  mov     [rcx+40h], r15d
0x1800058d5  mov     rcx, [rcx+30h]; hServiceStatus
0x1800058d9  mov     dword ptr [rdx+4], 3
0x1800058e0  call    cs:__imp_SetServiceStatus
0x1800058e6  test    eax, eax
0x1800058e8  jnz     short loc_18000592B
0x1800058ea  call    cs:__imp_GetLastError
0x1800058f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058f7  lea     rsi, WPP_GLOBAL_Control
0x1800058fe  cmp     rcx, rsi
0x180005901  jz      short loc_18000592B
0x180005903  mov     edi, 800h
0x180005908  test    [rcx+6Ch], edi
0x18000590b  jz      short loc_18000592B
0x18000590d  cmp     byte ptr [rcx+69h], 1
0x180005911  jb      short loc_18000592B
0x180005913  mov     rcx, [rcx+60h]
0x180005917  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x18000591e  mov     edx, 9Dh
0x180005923  mov     r9d, eax
0x180005926  call    WPP_SF_d
0x18000592b  lea     rcx, [rbx+60h]; this
0x18000592f  call    ?Set@Event@@QEAAXXZ; Event::Set(void)
0x180005934  xor     eax, eax
0x180005936  add     rsp, 28h
0x18000593a  pop     r15
0x18000593c  pop     r14
0x18000593e  pop     rdi
0x18000593f  pop     rsi
0x180005940  pop     rbp
0x180005941  pop     rbx
0x180005942  retn
```
