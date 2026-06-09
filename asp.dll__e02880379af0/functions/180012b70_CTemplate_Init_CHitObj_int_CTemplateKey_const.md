# CTemplate::Init(CHitObj *,int,CTemplateKey const &)

- ea: `0x180012b70`
- end: `0x180013089`
- name: `?Init@CTemplate@@QEAAJPEAVCHitObj@@HAEBUCTemplateKey@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(CTemplate *__hidden this, struct CHitObj *, int, const struct CTemplateKey *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800108d0`

## callees

- `0x180012b70`
- `0x180013090`
- `0x1800130b4`
- `0x180013178`
- `0x180013230`
- `0x18001324c`
- `0x1800132bc`
- `0x180023dd0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180012f97`
- `msvcrt!wcscpy_s` at `0x180012f97`
- `KERNEL32!HeapAlloc` at `0x180012f0c`
- `KERNEL32!HeapAlloc` at `0x180012f0c`
- `KERNEL32!CreateEventA` at `0x180012c6a`
- `KERNEL32!CreateEventA` at `0x180012c6a`
- `KERNEL32!DeleteCriticalSection` at `0x180012c49`
- `KERNEL32!DeleteCriticalSection` at `0x180012c49`
- `KERNEL32!GetLastError` at `0x180012bc3`
- `KERNEL32!GetLastError` at `0x180012c0e`
- `KERNEL32!GetLastError` at `0x180013027`
- `KERNEL32!GetLastError` at `0x180012bc3`
- `KERNEL32!GetLastError` at `0x180012c0e`
- `KERNEL32!GetLastError` at `0x180013027`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012db6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012dc7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012df6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012db6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012dc7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012df6`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d16`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d37`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d52`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d16`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d37`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180012d52`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012fe0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012fee`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012ffc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180013042`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180013050`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001305e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012fe0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012fee`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180012ffc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180013042`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180013050`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001305e`
- `iisutil!IISInitializeCriticalSection` at `0x180012bb9`
- `iisutil!IISInitializeCriticalSection` at `0x180012c04`
- `iisutil!IISInitializeCriticalSection` at `0x180012bb9`
- `iisutil!IISInitializeCriticalSection` at `0x180012c04`

## pseudocode

```c
__int64 __fastcall CTemplate::Init(
        CTemplate *this,
        struct CIsapiReqInfo **a2,
        unsigned __int8 a3,
        const struct CTemplateKey *a4)
{
  int ApplicationPath; // esi
  signed int LastError; // eax
  signed int v8; // eax
  HANDLE EventA; // rax
  struct CIsapiReqInfo *v11; // rax
  struct CIsapiReqInfo *v12; // rax
  const char *Ptr; // r13
  const char *v14; // r12
  int v15; // r15d
  int v16; // r9d
  int v17; // r9d
  unsigned __int16 *v18; // r14
  unsigned __int16 *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned __int64 v23; // r12
  SIZE_T v24; // rax
  unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rdx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // r9
  unsigned __int16 *v30; // rcx
  unsigned __int16 v31; // r8
  wchar_t *v32; // rax
  unsigned __int16 **v33; // rax
  unsigned __int16 *v34; // rax
  unsigned int v35; // [rsp+24h] [rbp-764h] BYREF
  unsigned int v36; // [rsp+28h] [rbp-760h] BYREF
  unsigned int v37; // [rsp+2Ch] [rbp-75Ch] BYREF
  CTemplate *v38; // [rsp+30h] [rbp-758h]
  struct CHitObj *v39; // [rsp+38h] [rbp-750h]
  __int64 v40; // [rsp+40h] [rbp-748h] BYREF
  const struct CTemplateKey *v41; // [rsp+48h] [rbp-740h]
  __int128 v42; // [rsp+58h] [rbp-730h] BYREF
  _BYTE v43[48]; // [rsp+68h] [rbp-720h] BYREF
  _BYTE v44[48]; // [rsp+98h] [rbp-6F0h] BYREF
  _BYTE v45[56]; // [rsp+C8h] [rbp-6C0h] BYREF
  unsigned __int16 *v46; // [rsp+100h] [rbp-688h] BYREF
  char v47; // [rsp+108h] [rbp-680h] BYREF
  int v48; // [rsp+308h] [rbp-480h]
  unsigned __int16 *v49; // [rsp+310h] [rbp-478h] BYREF
  char v50; // [rsp+318h] [rbp-470h] BYREF
  int v51; // [rsp+518h] [rbp-270h]
  _OWORD v52[2]; // [rsp+520h] [rbp-268h] BYREF
  wchar_t Source[256]; // [rsp+540h] [rbp-248h] BYREF

  v38 = this;
  v39 = (struct CHitObj *)a2;
  v41 = a4;
  ApplicationPath = 0;
  if ( !(unsigned int)IISInitializeCriticalSection((char *)this + 208) )
  {
    LastError = GetLastError();
    ApplicationPath = LastError;
    if ( LastError > 0 )
      ApplicationPath = (unsigned __int16)LastError | 0x80070000;
  }
  if ( ApplicationPath < 0 )
    return (unsigned int)ApplicationPath;
  ApplicationPath = 0;
  if ( !(unsigned int)IISInitializeCriticalSection((char *)this + 536) )
  {
    v8 = GetLastError();
    ApplicationPath = v8;
    if ( v8 > 0 )
      ApplicationPath = (unsigned __int16)v8 | 0x80070000;
  }
  if ( ApplicationPath >= 0 )
  {
    *((_DWORD *)this + 98) |= 0x8010u;
    EventA = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 7) = EventA;
    if ( !EventA )
      return 2147942414LL;
    *((_DWORD *)this + 98) ^= ((unsigned __int8)*((_DWORD *)this + 98) ^ a3) & 1;
    if ( !a2[8] )
      return 2147500035LL;
    v11 = a2[29];
    if ( !v11 )
      v11 = (struct CIsapiReqInfo *)*((_QWORD *)a2[3] + 19);
    *((_DWORD *)this + 100) = *((_DWORD *)v11 + 13);
    v12 = a2[29];
    if ( !v12 )
      v12 = (struct CIsapiReqInfo *)*((_QWORD *)a2[3] + 19);
    *((_DWORD *)this + 101) = *((_DWORD *)v12 + 24);
    memset(v52, 0, sizeof(v52));
    BUFFER::BUFFER((BUFFER *)v45, (unsigned __int8 *)v52, 0x20u);
    v42 = 0;
    BUFFER::BUFFER((BUFFER *)v44, (unsigned __int8 *)&v42, 0x10u);
    v40 = 0;
    BUFFER::BUFFER((BUFFER *)v43, (unsigned __int8 *)&v40, 8u);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    if ( (unsigned int)SERVER_GET(a2[8], "SERVER_NAME", (struct BUFFER *)v45, &v35)
      && (unsigned int)SERVER_GET(a2[8], "SERVER_PORT", (struct BUFFER *)v44, &v36) )
    {
      Ptr = (const char *)BUFFER::QueryPtr((BUFFER *)v44);
      v14 = (const char *)BUFFER::QueryPtr((BUFFER *)v45);
      v15 = 0;
      if ( (unsigned int)SERVER_GET(a2[8], "SERVER_PORT_SECURE", (struct BUFFER *)v43, &v37) )
        LOBYTE(v15) = *(_BYTE *)BUFFER::QueryPtr((BUFFER *)v43) == 49;
      ApplicationPath = FindApplicationPath(a2[8], Source, 512);
      if ( ApplicationPath >= 0 )
      {
        v46 = (unsigned __int16 *)&v47;
        v48 = 0;
        ApplicationPath = CMBCSToWChar::Init((LPVOID *)&v46, v14, 0, v16);
        if ( ApplicationPath >= 0 )
        {
          v18 = v46;
          v49 = (unsigned __int16 *)&v50;
          v51 = 0;
          ApplicationPath = CMBCSToWChar::Init((LPVOID *)&v49, Ptr, 0, v17);
          if ( ApplicationPath >= 0 )
          {
            v19 = v49;
            v20 = -1;
            do
              ++v20;
            while ( Source[v20] );
            v21 = -1;
            do
              ++v21;
            while ( v18[v21] );
            v22 = -1;
            do
              ++v22;
            while ( v49[v22] );
            v23 = (unsigned int)(v21 + 10 + v20 + v22);
            v24 = 2 * v23;
            if ( !is_mul_ok(v23, 2u) )
              v24 = -1;
            v25 = (unsigned __int16 *)HeapAlloc(g_hDenaliHeap, 0, v24);
            *((_QWORD *)this + 48) = v25;
            if ( v25 )
            {
              v26 = L"https://";
              if ( !v15 )
                v26 = L"http://";
              v27 = strcpyExW(v25, v26);
              v28 = strcpyExW(v27, v18);
              do
              {
                v30 = v28;
                v31 = *v29++;
                *v28++ = v31;
              }
              while ( v31 );
              v32 = strcpyExW(v30, v19);
              *((_QWORD *)this + 47) = v32;
              wcscpy_s(v32, v23 - (((__int64)v32 - *((_QWORD *)this + 48)) >> 1), Source);
              v33 = (unsigned __int16 **)v41;
              *((_DWORD *)this + 72) = *((_DWORD *)v41 + 2);
              v34 = StringDupW(*v33, 0);
              *((_QWORD *)this + 35) = v34;
              if ( v34 )
              {
                CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v49);
                CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v46);
                BUFFER::~BUFFER((BUFFER *)v43);
                BUFFER::~BUFFER((BUFFER *)v44);
                BUFFER::~BUFFER((BUFFER *)v45);
                return 0;
              }
            }
            CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v49);
            CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v46);
            ApplicationPath = -2147024882;
            goto LABEL_45;
          }
          CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v49);
        }
        CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v46);
      }
    }
    else
    {
      ApplicationPath = -2147024882;
      if ( GetLastError() != 14 )
        ApplicationPath = -2147467259;
    }
LABEL_45:
    BUFFER::~BUFFER((BUFFER *)v43);
    BUFFER::~BUFFER((BUFFER *)v44);
    BUFFER::~BUFFER((BUFFER *)v45);
    return (unsigned int)ApplicationPath;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  return (unsigned int)ApplicationPath;
}

```

## disassembly

```asm
0x180012b70  mov     [rsp+arg_10], r8d
0x180012b75  push    rbx
0x180012b76  push    rsi
0x180012b77  push    rdi
0x180012b78  push    r12
0x180012b7a  push    r13
0x180012b7c  push    r14
0x180012b7e  push    r15
0x180012b80  sub     rsp, 750h
0x180012b87  mov     rax, cs:__security_cookie
0x180012b8e  xor     rax, rsp
0x180012b91  mov     [rsp+788h+var_48], rax
0x180012b99  mov     r14, rdx
0x180012b9c  mov     rdi, rcx
0x180012b9f  mov     [rsp+788h+var_758], rcx
0x180012ba4  mov     [rsp+788h+var_750], rdx
0x180012ba9  mov     [rsp+788h+var_740], r9
0x180012bae  xor     ebx, ebx
0x180012bb0  mov     esi, ebx
0x180012bb2  add     rcx, 0D0h
0x180012bb9  call    cs:__imp_IISInitializeCriticalSection
0x180012bbf  test    eax, eax
0x180012bc1  jnz     short loc_180012BDC
0x180012bc3  call    cs:__imp_GetLastError
0x180012bc9  mov     esi, eax
0x180012bcb  test    eax, eax
0x180012bcd  jle     short loc_180012BD8
0x180012bcf  movzx   esi, ax
0x180012bd2  or      esi, 80070000h
0x180012bd8  mov     [rsp+788h+var_768], esi
0x180012bdc  jmp     short loc_180012BF3
0x180012bde  mov     esi, 8000FFFFh
0x180012be3  mov     [rsp+788h+var_768], esi
0x180012be7  xor     ebx, ebx
0x180012be9  mov     rdi, [rsp+788h+var_758]
0x180012bee  mov     r14, [rsp+788h+var_750]
0x180012bf3  test    esi, esi
0x180012bf5  js      loc_180013064
0x180012bfb  mov     esi, ebx
0x180012bfd  lea     rcx, [rdi+218h]
0x180012c04  call    cs:__imp_IISInitializeCriticalSection
0x180012c0a  test    eax, eax
0x180012c0c  jnz     short loc_180012C27
0x180012c0e  call    cs:__imp_GetLastError
0x180012c14  mov     esi, eax
0x180012c16  test    eax, eax
0x180012c18  jle     short loc_180012C23
0x180012c1a  movzx   esi, ax
0x180012c1d  or      esi, 80070000h
0x180012c23  mov     [rsp+788h+var_768], esi
0x180012c27  jmp     short loc_180012C3E
0x180012c29  mov     esi, 8000FFFFh
0x180012c2e  mov     [rsp+788h+var_768], esi
0x180012c32  xor     ebx, ebx
0x180012c34  mov     rdi, [rsp+788h+var_758]
0x180012c39  mov     r14, [rsp+788h+var_750]
0x180012c3e  test    esi, esi
0x180012c40  jns     short loc_180012C54
0x180012c42  lea     rcx, [rdi+0D0h]; lpCriticalSection
0x180012c49  call    cs:__imp_DeleteCriticalSection
0x180012c4f  jmp     loc_180013064
0x180012c54  or      dword ptr [rdi+188h], 8010h
0x180012c5e  xor     r9d, r9d; lpName
0x180012c61  xor     r8d, r8d; bInitialState
0x180012c64  lea     edx, [r9+1]; bManualReset
0x180012c68  xor     ecx, ecx; lpEventAttributes
0x180012c6a  call    cs:__imp_CreateEventA
0x180012c70  mov     [rdi+38h], rax
0x180012c74  test    rax, rax
0x180012c77  jnz     short loc_180012C83
0x180012c79  mov     eax, 8007000Eh
0x180012c7e  jmp     loc_180013066
0x180012c83  mov     eax, [rdi+188h]
0x180012c89  mov     cl, byte ptr [rsp+788h+arg_10]
0x180012c90  xor     ecx, eax
0x180012c92  and     ecx, 1
0x180012c95  xor     ecx, eax
0x180012c97  mov     [rdi+188h], ecx
0x180012c9d  cmp     [r14+40h], rbx
0x180012ca1  jnz     short loc_180012CAD
0x180012ca3  mov     eax, 80004003h
0x180012ca8  jmp     loc_180013066
0x180012cad  mov     rax, [r14+0E8h]
0x180012cb4  test    rax, rax
0x180012cb7  jnz     short loc_180012CC4
0x180012cb9  mov     rax, [r14+18h]
0x180012cbd  mov     rax, [rax+98h]
0x180012cc4  mov     eax, [rax+34h]
0x180012cc7  mov     [rdi+190h], eax
0x180012ccd  mov     rax, [r14+0E8h]
0x180012cd4  test    rax, rax
0x180012cd7  jnz     short loc_180012CE4
0x180012cd9  mov     rax, [r14+18h]
0x180012cdd  mov     rax, [rax+98h]
0x180012ce4  mov     eax, [rax+60h]
0x180012ce7  mov     [rdi+194h], eax
0x180012ced  xorps   xmm0, xmm0
0x180012cf0  movups  [rsp+788h+var_268], xmm0
0x180012cf8  movups  [rsp+788h+var_258], xmm0
0x180012d00  mov     r8d, 20h ; ' '
0x180012d06  lea     rdx, [rsp+788h+var_268]
0x180012d0e  lea     rcx, [rsp+788h+var_6C0]
0x180012d16  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180012d1c  xorps   xmm0, xmm0
0x180012d1f  movups  [rsp+788h+var_730], xmm0
0x180012d24  mov     r8d, 10h
0x180012d2a  lea     rdx, [rsp+788h+var_730]
0x180012d2f  lea     rcx, [rsp+788h+var_6F0]
0x180012d37  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180012d3d  mov     [rsp+788h+var_748], rbx
0x180012d42  mov     r8d, 8
0x180012d48  lea     rdx, [rsp+788h+var_748]
0x180012d4d  lea     rcx, [rsp+788h+var_720]
0x180012d52  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180012d58  mov     [rsp+788h+var_764], ebx
0x180012d5c  mov     [rsp+788h+var_760], ebx
0x180012d60  mov     [rsp+788h+var_75C], ebx
0x180012d64  lea     r9, [rsp+788h+var_764]; unsigned int *
0x180012d69  lea     r8, [rsp+788h+var_6C0]; struct BUFFER *
0x180012d71  lea     rdx, aServerName_0; "SERVER_NAME"
0x180012d78  mov     rcx, [r14+40h]; struct CIsapiReqInfo *
0x180012d7c  call    ?SERVER_GET@@YAHPEAVCIsapiReqInfo@@PEBDPEAVBUFFER@@PEAK@Z; SERVER_GET(CIsapiReqInfo *,char const *,BUFFER *,ulong *)
0x180012d81  test    eax, eax
0x180012d83  jz      loc_180013027
0x180012d89  lea     r9, [rsp+788h+var_760]; unsigned int *
0x180012d8e  lea     r8, [rsp+788h+var_6F0]; struct BUFFER *
0x180012d96  lea     rdx, aServerPort_0; "SERVER_PORT"
0x180012d9d  mov     rcx, [r14+40h]; struct CIsapiReqInfo *
0x180012da1  call    ?SERVER_GET@@YAHPEAVCIsapiReqInfo@@PEBDPEAVBUFFER@@PEAK@Z; SERVER_GET(CIsapiReqInfo *,char const *,BUFFER *,ulong *)
0x180012da6  test    eax, eax
0x180012da8  jz      loc_180013027
0x180012dae  lea     rcx, [rsp+788h+var_6F0]
0x180012db6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180012dbc  mov     r13, rax
0x180012dbf  lea     rcx, [rsp+788h+var_6C0]
0x180012dc7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180012dcd  mov     r12, rax
0x180012dd0  mov     r15d, ebx
0x180012dd3  lea     r9, [rsp+788h+var_75C]; unsigned int *
0x180012dd8  lea     r8, [rsp+788h+var_720]; struct BUFFER *
0x180012ddd  lea     rdx, aServerPortSecu_0; "SERVER_PORT_SECURE"
0x180012de4  mov     rcx, [r14+40h]; struct CIsapiReqInfo *
0x180012de8  call    ?SERVER_GET@@YAHPEAVCIsapiReqInfo@@PEBDPEAVBUFFER@@PEAK@Z; SERVER_GET(CIsapiReqInfo *,char const *,BUFFER *,ulong *)
0x180012ded  test    eax, eax
0x180012def  jz      short loc_180012E03
0x180012df1  lea     rcx, [rsp+788h+var_720]
0x180012df6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180012dfc  cmp     byte ptr [rax], 31h ; '1'
0x180012dff  setz    r15b
0x180012e03  mov     r8d, 200h; int
0x180012e09  lea     rdx, [rsp+788h+Source]; unsigned __int16 *
0x180012e11  mov     rcx, [r14+40h]; struct CIsapiReqInfo *
0x180012e15  call    ?FindApplicationPath@@YAJPEAVCIsapiReqInfo@@PEAGH@Z; FindApplicationPath(CIsapiReqInfo *,ushort *,int)
0x180012e1a  mov     esi, eax
0x180012e1c  test    eax, eax
0x180012e1e  js      loc_18001303D
0x180012e24  lea     rax, [rsp+788h+var_680]
0x180012e2c  mov     [rsp+788h+var_688], rax
0x180012e34  mov     [rsp+788h+var_480], ebx
0x180012e3b  xor     r8d, r8d; unsigned int
0x180012e3e  mov     rdx, r12; char *
0x180012e41  lea     rcx, [rsp+788h+var_688]; this
0x180012e49  call    ?Init@CMBCSToWChar@@QEAAJPEBDIH@Z; CMBCSToWChar::Init(char const *,uint,int)
0x180012e4e  mov     esi, eax
0x180012e50  test    eax, eax
0x180012e52  jns     short loc_180012E66
0x180012e54  lea     rcx, [rsp+788h+var_688]; this
0x180012e5c  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180012e61  jmp     loc_18001303D
0x180012e66  mov     r14, [rsp+788h+var_688]
0x180012e6e  lea     rax, [rsp+788h+var_470]
0x180012e76  mov     [rsp+788h+var_478], rax
0x180012e7e  mov     [rsp+788h+var_270], ebx
0x180012e85  xor     r8d, r8d; unsigned int
0x180012e88  mov     rdx, r13; char *
0x180012e8b  lea     rcx, [rsp+788h+var_478]; this
0x180012e93  call    ?Init@CMBCSToWChar@@QEAAJPEBDIH@Z; CMBCSToWChar::Init(char const *,uint,int)
0x180012e98  mov     esi, eax
0x180012e9a  test    eax, eax
0x180012e9c  jns     short loc_180012EAD
0x180012e9e  lea     rcx, [rsp+788h+var_478]; this
0x180012ea6  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180012eab  jmp     short loc_180012E54
0x180012ead  mov     rsi, [rsp+788h+var_478]
0x180012eb5  lea     rax, [rsp+788h+Source]
0x180012ebd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012ec1  mov     rcx, r8
0x180012ec4  inc     rcx
0x180012ec7  cmp     [rax+rcx*2], bx
0x180012ecb  jnz     short loc_180012EC4
0x180012ecd  mov     rdx, r8
0x180012ed0  inc     rdx
0x180012ed3  cmp     [r14+rdx*2], bx
0x180012ed8  jnz     short loc_180012ED0
0x180012eda  mov     rax, r8
0x180012edd  inc     rax
0x180012ee0  cmp     [rsi+rax*2], bx
0x180012ee4  jnz     short loc_180012EDD
0x180012ee6  lea     r12, [rcx+rax]
0x180012eea  add     rdx, 0Ah
0x180012eee  add     r12, rdx
0x180012ef1  mov     r12d, r12d
0x180012ef4  mov     eax, 2
0x180012ef9  mul     r12
0x180012efc  cmovb   rax, r8
0x180012f00  mov     r8, rax; dwBytes
0x180012f03  xor     edx, edx; dwFlags
0x180012f05  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180012f0c  call    cs:__imp_HeapAlloc
0x180012f12  mov     [rdi+180h], rax
0x180012f19  test    rax, rax
0x180012f1c  jz      loc_180013006
0x180012f22  lea     rcx, aHttp; "http://"
0x180012f29  lea     rdx, aHttps; "https://"
0x180012f30  test    r15d, r15d
0x180012f33  cmovz   rdx, rcx; unsigned __int16 *
0x180012f37  mov     rcx, rax; unsigned __int16 *
0x180012f3a  call    ?strcpyExW@@YAPEAGPEAGPEBG@Z; strcpyExW(ushort *,ushort const *)
0x180012f3f  lea     r9, asc_18006A708; ":"
0x180012f46  mov     rdx, r14; unsigned __int16 *
0x180012f49  mov     rcx, rax; unsigned __int16 *
0x180012f4c  call    ?strcpyExW@@YAPEAGPEAGPEBG@Z; strcpyExW(ushort *,ushort const *)
0x180012f51  mov     rcx, rax; unsigned __int16 *
0x180012f54  movzx   r8d, word ptr [r9]
0x180012f58  lea     r9, [r9+2]
0x180012f5c  mov     [rax], r8w
0x180012f60  add     rax, 2
0x180012f64  test    r8w, r8w
0x180012f68  jnz     short loc_180012F51
0x180012f6a  mov     rdx, rsi; unsigned __int16 *
0x180012f6d  call    ?strcpyExW@@YAPEAGPEAGPEBG@Z; strcpyExW(ushort *,ushort const *)
0x180012f72  mov     [rdi+178h], rax
0x180012f79  mov     rcx, rax
0x180012f7c  sub     rcx, [rdi+180h]
0x180012f83  sar     rcx, 1
0x180012f86  sub     r12, rcx
0x180012f89  lea     r8, [rsp+788h+Source]; Source
0x180012f91  mov     rdx, r12; SizeInWords
0x180012f94  mov     rcx, rax; Destination
0x180012f97  call    cs:__imp_wcscpy_s
0x180012f9d  mov     rax, [rsp+788h+var_740]
0x180012fa2  mov     ecx, [rax+8]
0x180012fa5  mov     [rdi+120h], ecx
0x180012fab  xor     edx, edx; int
0x180012fad  mov     rcx, [rax]; Src
0x180012fb0  call    ?StringDupW@@YAPEAGPEAGH@Z; StringDupW(ushort *,int)
0x180012fb5  mov     [rdi+118h], rax
0x180012fbc  test    rax, rax
0x180012fbf  jz      short loc_180013006
0x180012fc1  lea     rcx, [rsp+788h+var_478]; this
0x180012fc9  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180012fce  lea     rcx, [rsp+788h+var_688]; this
0x180012fd6  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180012fdb  lea     rcx, [rsp+788h+var_720]
0x180012fe0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180012fe6  lea     rcx, [rsp+788h+var_6F0]
0x180012fee  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180012ff4  lea     rcx, [rsp+788h+var_6C0]
0x180012ffc  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013002  xor     eax, eax
0x180013004  jmp     short loc_180013066
0x180013006  lea     rcx, [rsp+788h+var_478]; this
0x18001300e  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180013013  lea     rcx, [rsp+788h+var_688]; this
0x18001301b  call    ??1CMBCSToWChar@@QEAA@XZ; CMBCSToWChar::~CMBCSToWChar(void)
0x180013020  mov     esi, 8007000Eh
0x180013025  jmp     short loc_18001303D
0x180013027  call    cs:__imp_GetLastError
0x18001302d  mov     esi, 8007000Eh
0x180013032  mov     edx, 80004005h
0x180013037  cmp     eax, 0Eh
0x18001303a  cmovnz  esi, edx
0x18001303d  lea     rcx, [rsp+788h+var_720]
0x180013042  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013048  lea     rcx, [rsp+788h+var_6F0]
0x180013050  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013056  lea     rcx, [rsp+788h+var_6C0]
0x18001305e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013064  mov     eax, esi
0x180013066  mov     rcx, [rsp+788h+var_48]
0x18001306e  xor     rcx, rsp; StackCookie
0x180013071  call    __security_check_cookie
0x180013076  add     rsp, 750h
0x18001307d  pop     r15
0x18001307f  pop     r14
0x180013081  pop     r13
0x180013083  pop     r12
0x180013085  pop     rdi
0x180013086  pop     rsi
0x180013087  pop     rbx
0x180013088  retn
```
