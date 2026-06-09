# ConfigureGlobalJetParameters(void)

- ea: `0x1800b1600`
- end: `0x1800b1810`
- name: `?ConfigureGlobalJetParameters@@YAJXZ`
- size: `528`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800b0214`
- `0x1800b26b8`

## callees

- `0x18007ec9c`
- `0x1800b1600`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b17f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b17f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1650`
- `ESENT!JetSetSystemParameterW` at `0x1800b167f`
- `ESENT!JetSetSystemParameterW` at `0x1800b16bd`
- `ESENT!JetSetSystemParameterW` at `0x1800b16ed`
- `ESENT!JetSetSystemParameterW` at `0x1800b171d`
- `ESENT!JetSetSystemParameterW` at `0x1800b1750`
- `ESENT!JetSetSystemParameterW` at `0x1800b177f`
- `ESENT!JetSetSystemParameterW` at `0x1800b17ac`
- `ESENT!JetSetSystemParameterW` at `0x1800b167f`
- `ESENT!JetSetSystemParameterW` at `0x1800b16bd`
- `ESENT!JetSetSystemParameterW` at `0x1800b16ed`
- `ESENT!JetSetSystemParameterW` at `0x1800b171d`
- `ESENT!JetSetSystemParameterW` at `0x1800b1750`
- `ESENT!JetSetSystemParameterW` at `0x1800b177f`
- `ESENT!JetSetSystemParameterW` at `0x1800b17ac`

## pseudocode

```c
__int64 ConfigureGlobalJetParameters(void)
{
  int v0; // ebx
  JET_ERR v1; // eax
  JET_ERR v2; // eax
  JET_ERR v3; // eax
  JET_ERR v4; // eax
  JET_ERR v5; // eax
  JET_ERR v6; // eax
  JET_ERR v7; // eax
  JET_INSTANCE pinstance; // [rsp+30h] [rbp-18h] BYREF

  pinstance = -1;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 10, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids);
  EnterCriticalSection(&g_csGlobalJetParametersInit);
  if ( g_fGlobalJetParametersInitialized || (v1 = JetSetSystemParameterW(&pinstance, 0, 0x81u, 0, 0), v1 == -1030) )
  {
    v0 = 0;
  }
  else
  {
    v0 = HRESULTFromJET_ERR(v1, 0);
    if ( v0 >= 0 )
    {
      v2 = JetSetSystemParameterW(&pinstance, 0, 0x82u, 1u, 0);
      v0 = HRESULTFromJET_ERR(v2, 0);
      if ( v0 >= 0 )
      {
        v3 = JetSetSystemParameterW(&pinstance, 0, 0x7Eu, 1u, 0);
        v0 = HRESULTFromJET_ERR(v3, 0);
        if ( v0 >= 0 )
        {
          v4 = JetSetSystemParameterW(&pinstance, 0, 0x7Fu, 1u, 0);
          v0 = HRESULTFromJET_ERR(v4, 0);
          if ( v0 >= 0 )
          {
            v5 = JetSetSystemParameterW(&pinstance, 0, 0x40u, 0x8000u, 0);
            v0 = HRESULTFromJET_ERR(v5, 0);
            if ( v0 >= 0 )
            {
              v6 = JetSetSystemParameterW(&pinstance, 0, 0x17u, 0x800u, 0);
              v0 = HRESULTFromJET_ERR(v6, 0);
              if ( v0 >= 0 )
              {
                v7 = JetSetSystemParameterW(&pinstance, 0, 0x3Cu, 0x40u, 0);
                v0 = HRESULTFromJET_ERR(v7, 0);
                if ( v0 >= 0 )
                  g_fGlobalJetParametersInitialized = 1;
              }
            }
          }
        }
      }
    }
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 11, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)v0);
  LeaveCriticalSection(&g_csGlobalJetParametersInit);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800b1600  mov     [rsp+arg_0], rbx
0x1800b1605  push    rsi
0x1800b1606  sub     rsp, 40h
0x1800b160a  mov     rax, cs:__security_cookie
0x1800b1611  xor     rax, rsp
0x1800b1614  mov     [rsp+48h+var_10], rax
0x1800b1619  mov     dword ptr [rsp+48h+pinstance+4], 0
0x1800b1621  mov     qword ptr [rsp+30h], 0FFFFFFFFFFFFFFFFh
0x1800b162a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b1631  jz      short loc_1800B1649
0x1800b1633  mov     edx, 0Ah
0x1800b1638  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800b163f  mov     ecx, 40Ch
0x1800b1644  call    WPP_SF_
0x1800b1649  lea     rcx, ?g_csGlobalJetParametersInit@@3VWxCriticalSection@@A; lpCriticalSection
0x1800b1650  call    cs:__imp_EnterCriticalSection
0x1800b1656  cmp     cs:?g_fGlobalJetParametersInitialized@@3HA, 0; int g_fGlobalJetParametersInitialized
0x1800b165d  jz      short loc_1800B1666
0x1800b165f  xor     ebx, ebx
0x1800b1661  jmp     loc_1800B17C7
0x1800b1666  xor     r9d, r9d; lParam
0x1800b1669  mov     [rsp+48h+szParam], 0; szParam
0x1800b1672  xor     edx, edx; sesid
0x1800b1674  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b1679  mov     r8d, 81h; paramid
0x1800b167f  call    cs:__imp_JetSetSystemParameterW
0x1800b1685  cmp     eax, 0FFFFFBFAh
0x1800b168a  jz      short loc_1800B165F
0x1800b168c  xor     edx, edx; int
0x1800b168e  mov     ecx, eax; int
0x1800b1690  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b1695  mov     ebx, eax
0x1800b1697  test    eax, eax
0x1800b1699  js      loc_1800B17C7
0x1800b169f  mov     esi, 1
0x1800b16a4  mov     [rsp+48h+szParam], 0; szParam
0x1800b16ad  mov     r9d, esi; lParam
0x1800b16b0  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b16b5  xor     edx, edx; sesid
0x1800b16b7  mov     r8d, 82h; paramid
0x1800b16bd  call    cs:__imp_JetSetSystemParameterW
0x1800b16c3  mov     ecx, eax; int
0x1800b16c5  xor     edx, edx; int
0x1800b16c7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b16cc  mov     ebx, eax
0x1800b16ce  test    eax, eax
0x1800b16d0  js      loc_1800B17C7
0x1800b16d6  mov     r9d, esi; lParam
0x1800b16d9  mov     [rsp+48h+szParam], 0; szParam
0x1800b16e2  xor     edx, edx; sesid
0x1800b16e4  lea     r8d, [rsi+7Dh]; paramid
0x1800b16e8  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b16ed  call    cs:__imp_JetSetSystemParameterW
0x1800b16f3  mov     ecx, eax; int
0x1800b16f5  xor     edx, edx; int
0x1800b16f7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b16fc  mov     ebx, eax
0x1800b16fe  test    eax, eax
0x1800b1700  js      loc_1800B17C7
0x1800b1706  mov     r9d, esi; lParam
0x1800b1709  mov     [rsp+48h+szParam], 0; szParam
0x1800b1712  xor     edx, edx; sesid
0x1800b1714  lea     r8d, [rsi+7Eh]; paramid
0x1800b1718  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b171d  call    cs:__imp_JetSetSystemParameterW
0x1800b1723  mov     ecx, eax; int
0x1800b1725  xor     edx, edx; int
0x1800b1727  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b172c  mov     ebx, eax
0x1800b172e  test    eax, eax
0x1800b1730  js      loc_1800B17C7
0x1800b1736  xor     edx, edx; sesid
0x1800b1738  mov     [rsp+48h+szParam], 0; szParam
0x1800b1741  mov     r9d, 8000h; lParam
0x1800b1747  lea     r8d, [rsi+3Fh]; paramid
0x1800b174b  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b1750  call    cs:__imp_JetSetSystemParameterW
0x1800b1756  mov     ecx, eax; int
0x1800b1758  xor     edx, edx; int
0x1800b175a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b175f  mov     ebx, eax
0x1800b1761  test    eax, eax
0x1800b1763  js      short loc_1800B17C7
0x1800b1765  xor     edx, edx; sesid
0x1800b1767  mov     [rsp+48h+szParam], 0; szParam
0x1800b1770  mov     r9d, 800h; lParam
0x1800b1776  lea     r8d, [rsi+16h]; paramid
0x1800b177a  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b177f  call    cs:__imp_JetSetSystemParameterW
0x1800b1785  mov     ecx, eax; int
0x1800b1787  xor     edx, edx; int
0x1800b1789  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b178e  mov     ebx, eax
0x1800b1790  test    eax, eax
0x1800b1792  js      short loc_1800B17C7
0x1800b1794  xor     edx, edx; sesid
0x1800b1796  mov     [rsp+48h+szParam], 0; szParam
0x1800b179f  lea     r9d, [rsi+3Fh]; lParam
0x1800b17a3  lea     r8d, [rsi+3Bh]; paramid
0x1800b17a7  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1800b17ac  call    cs:__imp_JetSetSystemParameterW
0x1800b17b2  mov     ecx, eax; int
0x1800b17b4  xor     edx, edx; int
0x1800b17b6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b17bb  mov     ebx, eax
0x1800b17bd  test    eax, eax
0x1800b17bf  js      short loc_1800B17C7
0x1800b17c1  mov     cs:?g_fGlobalJetParametersInitialized@@3HA, esi; int g_fGlobalJetParametersInitialized
0x1800b17c7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b17ce  jz      short loc_1800B17E9
0x1800b17d0  mov     edx, 0Bh
0x1800b17d5  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800b17dc  mov     ecx, 40Ch
0x1800b17e1  mov     r9d, ebx
0x1800b17e4  call    WPP_SF_d
0x1800b17e9  lea     rcx, ?g_csGlobalJetParametersInit@@3VWxCriticalSection@@A; lpCriticalSection
0x1800b17f0  call    cs:__imp_LeaveCriticalSection
0x1800b17f6  mov     eax, ebx
0x1800b17f8  mov     rcx, [rsp+48h+var_10]
0x1800b17fd  xor     rcx, rsp; StackCookie
0x1800b1800  call    __security_check_cookie
0x1800b1805  mov     rbx, [rsp+48h+arg_0]
0x1800b180a  add     rsp, 40h
0x1800b180e  pop     rsi
0x1800b180f  retn
```
