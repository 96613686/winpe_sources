# CTnoCfgMgr::OpenKeys(void)

- ea: `0x180024478`
- end: `0x1800245a5`
- name: `?OpenKeys@CTnoCfgMgr@@AEAAKXZ`
- size: `301`
- prototype: `unsigned int __fastcall(CTnoCfgMgr *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021680`
- `0x180027bfc`

## callees

- `0x180004510`
- `0x180004874`
- `0x18000cf48`
- `0x180021310`
- `0x180024478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800244d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024548`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800244d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024548`

## pseudocode

```c
__int64 __fastcall CTnoCfgMgr::OpenKeys(CTnoCfgMgr *this)
{
  _QWORD *v2; // rdi
  HKEY *phkResult; // rsi
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  _BYTE v8[72]; // [rsp+30h] [rbp-48h] BYREF

  InCritSec::InCritSec((InCritSec *)v8, this, 1);
  v2 = (_QWORD *)((char *)this + 320);
  AutoRegKey::Close((CTnoCfgMgr *)((char *)this + 320));
  phkResult = (HKEY *)((char *)this + 288);
  AutoRegKey::Close((CTnoCfgMgr *)((char *)this + 288));
  *((_WORD *)this + 68) = 257;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
         0,
         0x20119u,
         (PHKEY)this + 40);
  v5 = v4;
  if ( v4
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      70,
      (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
      v4);
  }
  if ( !*v2 )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x110u, phkResult);
    v5 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          71,
          (unsigned int)WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids,
          (unsigned int)L"Software\\Microsoft\\Windows NT\\CurrentVersion",
          v6);
      }
    }
  }
  InCritSec::~InCritSec((InCritSec *)v8);
  return v5;
}

```

## disassembly

```asm
0x180024478  push    rbx
0x18002447a  push    rsi
0x18002447b  push    rdi
0x18002447c  push    r14
0x18002447e  sub     rsp, 58h
0x180024482  mov     rbx, rcx
0x180024485  mov     rdx, rcx; struct CritSec *
0x180024488  lea     rcx, [rsp+78h+var_48]; this
0x18002448d  mov     r8b, 1; bool
0x180024490  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180024495  lea     rdi, [rbx+140h]
0x18002449c  mov     rcx, rdi; this
0x18002449f  call    ?Close@AutoRegKey@@QEAAXXZ; AutoRegKey::Close(void)
0x1800244a4  lea     rsi, [rbx+120h]
0x1800244ab  mov     rcx, rsi; this
0x1800244ae  call    ?Close@AutoRegKey@@QEAAXXZ; AutoRegKey::Close(void)
0x1800244b3  mov     r9d, 20119h; samDesired
0x1800244b9  mov     word ptr [rbx+88h], 101h
0x1800244c2  xor     r8d, r8d; ulOptions
0x1800244c5  mov     [rsp+78h+phkResult], rdi; phkResult
0x1800244ca  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800244d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800244d8  call    cs:__imp_RegOpenKeyExW
0x1800244de  lea     r14, WPP_GLOBAL_Control
0x1800244e5  mov     ebx, eax
0x1800244e7  test    eax, eax
0x1800244e9  jz      short loc_180024526
0x1800244eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244f2  cmp     rcx, r14
0x1800244f5  jz      short loc_180024526
0x1800244f7  test    dword ptr [rcx+6Ch], 200h
0x1800244fe  jz      short loc_180024526
0x180024500  cmp     byte ptr [rcx+69h], 1
0x180024504  jb      short loc_180024526
0x180024506  mov     rcx, [rcx+60h]
0x18002450a  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180024511  mov     edx, 46h ; 'F'
0x180024516  mov     dword ptr [rsp+78h+phkResult], eax
0x18002451a  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x180024521  call    WPP_SF_Sd
0x180024526  cmp     qword ptr [rdi], 0
0x18002452a  jnz     short loc_18002458F
0x18002452c  mov     r9d, 110h; samDesired
0x180024532  mov     [rsp+78h+phkResult], rsi; phkResult
0x180024537  xor     r8d, r8d; ulOptions
0x18002453a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180024541  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024548  call    cs:__imp_RegOpenKeyExW
0x18002454e  mov     ebx, eax
0x180024550  test    eax, eax
0x180024552  jz      short loc_18002458F
0x180024554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002455b  cmp     rcx, r14
0x18002455e  jz      short loc_18002458F
0x180024560  test    dword ptr [rcx+6Ch], 200h
0x180024567  jz      short loc_18002458F
0x180024569  cmp     byte ptr [rcx+69h], 1
0x18002456d  jb      short loc_18002458F
0x18002456f  mov     rcx, [rcx+60h]
0x180024573  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002457a  mov     edx, 47h ; 'G'
0x18002457f  mov     dword ptr [rsp+78h+phkResult], eax
0x180024583  lea     r8, WPP_a13c6be54241313b7a07b9ccc7fdeaac_Traceguids
0x18002458a  call    WPP_SF_Sd
0x18002458f  lea     rcx, [rsp+78h+var_48]; this
0x180024594  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180024599  mov     eax, ebx
0x18002459b  add     rsp, 58h
0x18002459f  pop     r14
0x1800245a1  pop     rdi
0x1800245a2  pop     rsi
0x1800245a3  pop     rbx
0x1800245a4  retn
```
