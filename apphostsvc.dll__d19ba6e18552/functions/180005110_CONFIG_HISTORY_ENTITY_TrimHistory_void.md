# CONFIG_HISTORY_ENTITY::TrimHistory(void)

- ea: `0x180005110`
- end: `0x180005288`
- name: `?TrimHistory@CONFIG_HISTORY_ENTITY@@QEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(CONFIG_HISTORY_ENTITY *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004b0c`

## callees

- `0x180004528`
- `0x180004894`
- `0x1800048fc`
- `0x180005110`
- `0x180008c1f`
- `0x180008c50`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180005258`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005258`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000515e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000515e`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800051dc`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800051dc`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY_ENTITY::TrimHistory(CONFIG_HISTORY_ENTITY *this)
{
  int Path; // edi
  unsigned int v3; // ecx
  int v4; // ebp
  int v5; // esi
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // ecx
  _BYTE v10[32]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 *v11; // [rsp+40h] [rbp-258h]
  unsigned __int16 v12[264]; // [rsp+60h] [rbp-238h] BYREF

  Path = 0;
  memset_0(v12, 0, 0x20Au);
  STRU::STRU((STRU *)v10, v12, 0x105u);
  v3 = *((_DWORD *)this + 72);
  if ( v3 )
  {
    v4 = 0;
    v5 = 0;
    while ( v3 > *((_DWORD *)this + 71) - 1 )
    {
      v6 = *((_DWORD *)this + 73);
      if ( v6 == -1 )
        v4 = 1;
      if ( v6 <= *((_DWORD *)this + 74) )
      {
        *((_DWORD *)this + 73) = v6 + 1;
        Path = CONFIG_HISTORY_ENTITY::MakePath(this, (struct STRU *)v10, v6);
        if ( Path < 0 )
          break;
        Path = STRU::Append((STRU *)v10, 0);
        if ( Path < 0 )
          break;
        v7 = CONFIG_HISTORY_ENTITY::DeleteDirectory(this, v11);
        Path = v7;
        if ( v7 >= 0 )
          --*((_DWORD *)this + 72);
        if ( v4 )
          break;
        if ( v7 < 0 )
        {
          if ( v7 == -2147024893 )
          {
            if ( (unsigned int)++v5 > 5 )
            {
              Path = CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(this);
              if ( Path < 0 )
                break;
              v5 = 0;
            }
          }
          else
          {
            v8 = *((_DWORD *)this + 72);
            if ( v8 < *((_DWORD *)this + 71) + 1 )
              break;
            *((_DWORD *)this + 72) = v8 - 1;
          }
        }
      }
      else
      {
        Path = CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(this);
        if ( Path < 0 )
          break;
      }
      v3 = *((_DWORD *)this + 72);
      if ( !v3 )
        break;
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180005110  mov     [rsp+arg_8], rbx
0x180005115  mov     [rsp+arg_10], rbp
0x18000511a  push    rsi
0x18000511b  push    rdi
0x18000511c  push    r14
0x18000511e  sub     rsp, 280h
0x180005125  mov     rax, cs:__security_cookie
0x18000512c  xor     rax, rsp
0x18000512f  mov     [rsp+298h+var_28], rax
0x180005137  mov     rbx, rcx
0x18000513a  xor     edi, edi
0x18000513c  xor     edx, edx; Val
0x18000513e  mov     r8d, 20Ah; Size
0x180005144  lea     rcx, [rsp+298h+var_238]; void *
0x180005149  call    memset_0
0x18000514e  mov     r8d, 105h
0x180005154  lea     rdx, [rsp+298h+var_238]
0x180005159  lea     rcx, [rsp+298h+var_278]
0x18000515e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005164  nop
0x180005165  mov     ecx, [rbx+120h]
0x18000516b  test    ecx, ecx
0x18000516d  jz      loc_180005253
0x180005173  xor     ebp, ebp
0x180005175  xor     esi, esi
0x180005177  lea     r14d, [rdi+1]
0x18000517b  mov     eax, [rbx+11Ch]
0x180005181  sub     eax, r14d
0x180005184  cmp     ecx, eax
0x180005186  jbe     loc_180005253
0x18000518c  mov     r8d, [rbx+124h]; unsigned int
0x180005193  cmp     r8d, 0FFFFFFFFh
0x180005197  cmovz   ebp, r14d
0x18000519b  mov     rcx, rbx; this
0x18000519e  cmp     r8d, [rbx+128h]
0x1800051a5  jbe     short loc_1800051BB
0x1800051a7  call    ?ScanHistoryDirectory@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(void)
0x1800051ac  mov     edi, eax
0x1800051ae  test    eax, eax
0x1800051b0  js      loc_180005253
0x1800051b6  jmp     loc_180005245
0x1800051bb  lea     eax, [r8+1]
0x1800051bf  mov     [rbx+124h], eax
0x1800051c5  lea     rdx, [rsp+298h+var_278]; struct STRU *
0x1800051ca  call    ?MakePath@CONFIG_HISTORY_ENTITY@@QEAAJPEAVSTRU@@K@Z; CONFIG_HISTORY_ENTITY::MakePath(STRU *,ulong)
0x1800051cf  mov     edi, eax
0x1800051d1  test    eax, eax
0x1800051d3  js      short loc_180005253
0x1800051d5  xor     edx, edx
0x1800051d7  lea     rcx, [rsp+298h+var_278]
0x1800051dc  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800051e2  mov     edi, eax
0x1800051e4  test    eax, eax
0x1800051e6  js      short loc_180005253
0x1800051e8  mov     rdx, [rsp+298h+var_258]; unsigned __int16 *
0x1800051ed  mov     rcx, rbx; this
0x1800051f0  call    ?DeleteDirectory@CONFIG_HISTORY_ENTITY@@QEAAJPEBG@Z; CONFIG_HISTORY_ENTITY::DeleteDirectory(ushort const *)
0x1800051f5  mov     edi, eax
0x1800051f7  test    eax, eax
0x1800051f9  js      short loc_180005201
0x1800051fb  dec     dword ptr [rbx+120h]
0x180005201  test    ebp, ebp
0x180005203  jnz     short loc_180005253
0x180005205  test    eax, eax
0x180005207  jns     short loc_180005245
0x180005209  cmp     eax, 80070003h
0x18000520e  jnz     short loc_180005229
0x180005210  inc     esi
0x180005212  cmp     esi, 5
0x180005215  jbe     short loc_180005245
0x180005217  mov     rcx, rbx; this
0x18000521a  call    ?ScanHistoryDirectory@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::ScanHistoryDirectory(void)
0x18000521f  mov     edi, eax
0x180005221  test    eax, eax
0x180005223  js      short loc_180005253
0x180005225  xor     esi, esi
0x180005227  jmp     short loc_180005245
0x180005229  mov     ecx, [rbx+120h]
0x18000522f  mov     eax, [rbx+11Ch]
0x180005235  add     eax, r14d
0x180005238  cmp     ecx, eax
0x18000523a  jb      short loc_180005253
0x18000523c  lea     eax, [rcx-1]
0x18000523f  mov     [rbx+120h], eax
0x180005245  mov     ecx, [rbx+120h]
0x18000524b  test    ecx, ecx
0x18000524d  jnz     loc_18000517B
0x180005253  lea     rcx, [rsp+298h+var_278]
0x180005258  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000525e  mov     eax, edi
0x180005260  mov     rcx, [rsp+298h+var_28]
0x180005268  xor     rcx, rsp; StackCookie
0x18000526b  call    __security_check_cookie
0x180005270  lea     r11, [rsp+298h+var_18]
0x180005278  mov     rbx, [r11+28h]
0x18000527c  mov     rbp, [r11+30h]
0x180005280  mov     rsp, r11
0x180005283  pop     r14
0x180005285  pop     rdi
0x180005286  pop     rsi
0x180005287  retn
```
