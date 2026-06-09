# Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)

- ea: `0x180029084`
- end: `0x180029387`
- name: `?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z`
- size: `771`
- prototype: `__int64 __fastcall(struct IMultiLanguage2 *this, unsigned __int8 *, __int64, struct _SDP_STRING_TYPE_DATA *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024bd4`
- `0x1800257dc`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180028c44`
- `0x180029084`
- `0x180029390`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029243`
- `OLEAUT32!__imp_SysAllocString` at `0x180029243`
- `OLEAUT32!__imp_SysFreeString` at `0x180029350`
- `OLEAUT32!__imp_SysFreeString` at `0x180029350`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002914b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002914b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029106`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029106`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002922c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002922c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
        struct IMultiLanguage2 *this,
        unsigned __int8 *a2,
        __int64 a3,
        struct _SDP_STRING_TYPE_DATA *a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  __int16 v6; // r13
  unsigned int v7; // esi
  HRESULT v9; // r14d
  int Instance; // ebx
  SDP_SPECIFICTYPE length; // r15d
  int v13; // ecx
  int v14; // edx
  unsigned int v15; // r8d
  unsigned __int16 v16; // r9
  const OLECHAR *v17; // rcx
  BSTR v18; // rax
  OLECHAR *v19; // rsi
  ULONGLONG LowPart; // r13
  char v21; // r15
  SDP_TYPE type; // eax
  bool v23; // cf
  unsigned __int16 *v24; // [rsp+28h] [rbp-B1h]
  _SDP_ELEMENT_DATA ppv; // [rsp+40h] [rbp-99h] BYREF
  struct _SDP_ELEMENT_DATA v26; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v27[4]; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v28; // [rsp+74h] [rbp-65h]

  v6 = (__int16)a4;
  v7 = (unsigned int)a2;
  memset(&v26, 0, sizeof(v26));
  if ( !this || !(_DWORD)a2 || !a6 )
    return 87;
  memset_0(v27, 0, 0x6Cu);
  ppv.data.int128.LowPart = 0;
  v9 = CoInitializeEx(0, 2u);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147417850 )
    return (unsigned int)v9;
  Instance = CoCreateInstance(
               &CLSID_CMultiLanguage,
               0,
               1u,
               &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a,
               (LPVOID *)&ppv.data);
  if ( Instance >= 0 )
  {
    LOWORD(ppv.specificType) = 106;
    LOWORD(ppv.type) = 256;
    Instance = Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(
                 (Microsoft::Bluetooth::Services::BthServ *)ppv.data.int128.LowPart,
                 this,
                 (unsigned __int8 *)v7,
                 (unsigned int)&ppv.specificType,
                 (unsigned __int16 *)&ppv,
                 v24);
    if ( !Instance )
    {
      Instance = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(
                   (Microsoft::Bluetooth::Services::BthServ *)this,
                   (unsigned __int8 *)v7,
                   v6 + LOWORD(ppv.type),
                   &v26);
      if ( !Instance )
      {
        if ( v26.type != SDP_TYPE_STRING )
        {
          Instance = 87;
          goto LABEL_21;
        }
        length = v26.data.string.length;
        if ( !v26.data.string.length )
        {
          *(_DWORD *)a6 = 0;
          Instance = 0;
          goto LABEL_21;
        }
        v13 = 0;
        v14 = 59;
        while ( 1 )
        {
          v15 = (unsigned int)(v14 + v13) >> 1;
          v16 = qword_180039570[2 * v15];
          if ( LOWORD(ppv.specificType) == v16 )
            break;
          if ( LOWORD(ppv.specificType) <= v16 )
            v14 = v15 - 1;
          else
            v13 = v15 + 1;
          if ( v13 > v14 )
            goto LABEL_20;
        }
        v17 = (const OLECHAR *)qword_180039570[2 * ((unsigned int)(v14 + v13) >> 1) + 1];
        if ( !v17 )
        {
LABEL_20:
          Instance = 13;
          goto LABEL_21;
        }
        v18 = SysAllocString(v17);
        v19 = v18;
        if ( !v18 )
        {
          Instance = 1450;
          goto LABEL_21;
        }
        if ( (*(int (__fastcall **)(ULONGLONG, BSTR, _BYTE *))(*(_QWORD *)ppv.data.int128.LowPart + 56LL))(
               ppv.data.int128.LowPart,
               v18,
               v27) >= 0 )
        {
          LowPart = v26.data.int128.LowPart;
          ppv.data.string.length = 0;
          ppv.specificType = length;
          ppv.type = SDP_TYPE_NIL;
          v21 = *(_BYTE *)((unsigned int)(length - 1) + v26.data.int128.LowPart);
          if ( !(*(unsigned int (__fastcall **)(ULONGLONG, ULONG *, _QWORD, ULONGLONG, SDP_SPECIFICTYPE *, _QWORD, _SDP_ELEMENT_DATA *))(*(_QWORD *)ppv.data.int128.LowPart + 80LL))(
                  ppv.data.int128.LowPart,
                  &ppv.data.string.length,
                  v28,
                  v26.data.int128.LowPart,
                  &ppv.specificType,
                  0,
                  &ppv) )
          {
            type = ppv.type;
            if ( v21 )
              type = ++ppv.type;
            if ( a5 )
            {
              v23 = *(_DWORD *)a6 < (unsigned int)type;
              *(_DWORD *)a6 = type;
              if ( !v23 )
              {
                if ( (*(unsigned int (__fastcall **)(ULONGLONG, ULONG *, _QWORD, ULONGLONG, SDP_SPECIFICTYPE *, __int64, _SDP_ELEMENT_DATA *))(*(_QWORD *)ppv.data.int128.LowPart + 80LL))(
                       ppv.data.int128.LowPart,
                       &ppv.data.string.length,
                       v28,
                       LowPart,
                       &ppv.specificType,
                       a5,
                       &ppv) )
                {
                  Instance = 13;
                }
                else
                {
                  if ( v21 )
                    *(_WORD *)(a5 + 2LL * (unsigned int)ppv.type) = 0;
                  Instance = 0;
                }
                goto LABEL_42;
              }
            }
            else
            {
              *(_DWORD *)a6 = type;
            }
            Instance = 234;
          }
        }
LABEL_42:
        SysFreeString(v19);
      }
    }
  }
LABEL_21:
  if ( ppv.data.int128.LowPart )
  {
    (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)ppv.data.int128.LowPart + 16LL))(ppv.data.int128.LowPart);
    ppv.data.int128.LowPart = 0;
  }
  if ( v9 >= 0 )
    CoUninitialize();
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180029084  mov     [rsp-8+arg_10], rbx
0x180029089  push    rbp
0x18002908a  push    rsi
0x18002908b  push    rdi
0x18002908c  push    r12
0x18002908e  push    r13
0x180029090  push    r14
0x180029092  push    r15
0x180029094  lea     rbp, [rsp-17h]
0x180029099  sub     rsp, 0F0h
0x1800290a0  mov     rax, cs:__security_cookie
0x1800290a7  xor     rax, rsp
0x1800290aa  mov     [rbp+47h+var_40], rax
0x1800290ae  mov     r12, [rbp+47h+arg_20]
0x1800290b2  xor     eax, eax
0x1800290b4  mov     rdi, [rbp+47h+arg_28]
0x1800290b8  xorps   xmm0, xmm0
0x1800290bb  mov     [rbp+47h+var_B8], rax
0x1800290bf  movzx   r13d, r9w
0x1800290c3  mov     esi, edx
0x1800290c5  mov     r15, rcx
0x1800290c8  movups  xmmword ptr [rsp+120h+var_C8], xmm0
0x1800290cd  test    rcx, rcx
0x1800290d0  jz      loc_18002935B
0x1800290d6  test    edx, edx
0x1800290d8  jz      loc_18002935B
0x1800290de  test    rdi, rdi
0x1800290e1  jz      loc_18002935B
0x1800290e7  xor     edx, edx; Val
0x1800290e9  lea     r8d, [rax+6Ch]; Size
0x1800290ed  lea     rcx, [rbp+47h+var_B0]; void *
0x1800290f1  call    memset_0
0x1800290f6  mov     edx, 2; dwCoInit
0x1800290fb  mov     qword ptr [rsp+120h+var_E0.data], 0
0x180029104  xor     ecx, ecx; pvReserved
0x180029106  call    cs:__imp_CoInitializeEx
0x18002910c  mov     r14d, eax
0x18002910f  mov     eax, 80000000h
0x180029114  lea     ecx, [r14+rax]
0x180029118  test    eax, ecx
0x18002911a  jnz     short loc_18002912D
0x18002911c  cmp     r14d, 80010106h
0x180029123  jz      short loc_18002912D
0x180029125  mov     eax, r14d
0x180029128  jmp     loc_180029360
0x18002912d  xor     edx, edx; pUnkOuter
0x18002912f  lea     rax, [rsp+120h+var_E0.data]
0x180029134  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x18002913b  mov     [rsp+120h+ppv], rax; ppv
0x180029140  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180029147  lea     r8d, [rdx+1]; dwClsContext
0x18002914b  call    cs:__imp_CoCreateInstance
0x180029151  mov     ebx, eax
0x180029153  test    eax, eax
0x180029155  js      loc_180029208
0x18002915b  mov     rcx, qword ptr [rsp+120h+var_E0.data]; this
0x180029160  lea     r9, [rsp+120h+var_E0.specificType]; unsigned int
0x180029165  mov     eax, 6Ah ; 'j'
0x18002916a  mov     r8d, esi; unsigned __int8 *
0x18002916d  mov     word ptr [rsp+120h+var_E0.specificType], ax
0x180029172  mov     rdx, r15; struct IMultiLanguage2 *
0x180029175  mov     eax, 100h
0x18002917a  mov     word ptr [rsp+120h+var_E0.type], ax
0x18002917f  lea     rax, [rsp+120h+var_E0]
0x180029184  mov     [rsp+120h+ppv], rax; struct _SDP_ELEMENT_DATA *
0x180029189  call    ?GetLangBaseInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAUIMultiLanguage2@@PEAEKPEAG2@Z; Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(IMultiLanguage2 *,uchar *,ulong,ushort *,ushort *)
0x18002918e  mov     ebx, eax
0x180029190  test    eax, eax
0x180029192  jnz     short loc_180029208
0x180029194  movzx   r8d, word ptr [rsp+120h+var_E0.type]
0x18002919a  lea     r9, [rsp+120h+var_C8]; unsigned __int16
0x18002919f  add     r8w, r13w; unsigned int
0x1800291a3  mov     edx, esi; unsigned __int8 *
0x1800291a5  mov     rcx, r15; this
0x1800291a8  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x1800291ad  mov     ebx, eax
0x1800291af  test    eax, eax
0x1800291b1  jnz     short loc_180029208
0x1800291b3  cmp     dword ptr [rsp+120h+var_C8], 4
0x1800291b8  jz      short loc_1800291BF
0x1800291ba  lea     ebx, [rax+57h]
0x1800291bd  jmp     short loc_180029208
0x1800291bf  mov     r15, [rbp+47h+var_B8]
0x1800291c3  test    r15d, r15d
0x1800291c6  jnz     short loc_1800291CF
0x1800291c8  mov     [rdi], r15d
0x1800291cb  xor     ebx, ebx
0x1800291cd  jmp     short loc_180029208
0x1800291cf  xor     ecx, ecx
0x1800291d1  lea     r10, qword_180039570
0x1800291d8  lea     edx, [rcx+3Bh]
0x1800291db  lea     eax, [rdx+rcx]
0x1800291de  shr     eax, 1
0x1800291e0  mov     r8d, eax
0x1800291e3  add     rax, rax
0x1800291e6  movzx   r9d, word ptr [r10+rax*8]
0x1800291eb  cmp     word ptr [rsp+120h+var_E0.specificType], r9w
0x1800291f1  jz      short loc_180029239
0x1800291f3  jbe     short loc_1800291FB
0x1800291f5  lea     ecx, [r8+1]
0x1800291f9  jmp     short loc_1800291FF
0x1800291fb  lea     edx, [r8-1]
0x1800291ff  cmp     ecx, edx
0x180029201  jle     short loc_1800291DB
0x180029203  mov     ebx, 0Dh
0x180029208  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002920d  test    rcx, rcx
0x180029210  jz      short loc_180029227
0x180029212  mov     rax, [rcx]
0x180029215  mov     rax, [rax+10h]
0x180029219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002921e  mov     qword ptr [rsp+120h+var_E0.data], 0
0x180029227  test    r14d, r14d
0x18002922a  js      short loc_180029232
0x18002922c  call    cs:__imp_CoUninitialize
0x180029232  mov     eax, ebx
0x180029234  jmp     loc_180029360
0x180029239  mov     rcx, [r10+rax*8+8]; psz
0x18002923e  test    rcx, rcx
0x180029241  jz      short loc_180029203
0x180029243  call    cs:__imp_SysAllocString
0x180029249  mov     rsi, rax
0x18002924c  test    rax, rax
0x18002924f  jnz     short loc_180029258
0x180029251  mov     ebx, 5AAh
0x180029256  jmp     short loc_180029208
0x180029258  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002925d  lea     r8, [rbp+47h+var_B0]
0x180029261  mov     rdx, rsi
0x180029264  mov     rax, [rcx]
0x180029267  mov     rax, [rax+38h]
0x18002926b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029270  test    eax, eax
0x180029272  js      loc_18002934D
0x180029278  mov     r13, qword ptr [rbp+47h+var_C8+8]
0x18002927c  lea     eax, [r15-1]
0x180029280  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x180029285  lea     rdx, [rsp+120h+var_E0]
0x18002928a  mov     r8d, [rbp+47h+var_AC]
0x18002928e  mov     r9, r13
0x180029291  mov     [rsp+120h+var_F0], rdx
0x180029296  lea     rdx, [rsp+120h+var_E0.specificType]
0x18002929b  mov     dword ptr [rsp+120h+var_E0.data+8], 0
0x1800292a3  mov     [rsp+120h+var_E0.specificType], r15d
0x1800292a8  mov     [rsp+120h+var_E0.type], 0
0x1800292b0  mov     r15b, [rax+r13]
0x1800292b4  mov     rax, [rcx]
0x1800292b7  mov     [rsp+120h+var_F8], 0
0x1800292c0  mov     [rsp+120h+ppv], rdx
0x1800292c5  lea     rdx, [rsp+120h+var_E0.data+8]
0x1800292ca  mov     rax, [rax+50h]
0x1800292ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292d3  test    eax, eax
0x1800292d5  jnz     short loc_18002934D
0x1800292d7  mov     eax, [rsp+120h+var_E0.type]
0x1800292db  test    r15b, r15b
0x1800292de  jz      short loc_1800292E6
0x1800292e0  inc     eax
0x1800292e2  mov     [rsp+120h+var_E0.type], eax
0x1800292e6  test    r12, r12
0x1800292e9  jnz     short loc_1800292EF
0x1800292eb  mov     [rdi], eax
0x1800292ed  jmp     short loc_1800292F5
0x1800292ef  cmp     [rdi], eax
0x1800292f1  mov     [rdi], eax
0x1800292f3  jnb     short loc_1800292FC
0x1800292f5  mov     ebx, 0EAh
0x1800292fa  jmp     short loc_18002934D
0x1800292fc  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x180029301  lea     rdx, [rsp+120h+var_E0]
0x180029306  mov     r8d, [rbp+47h+var_AC]
0x18002930a  mov     r9, r13
0x18002930d  mov     [rsp+120h+var_F0], rdx
0x180029312  lea     rdx, [rsp+120h+var_E0.specificType]
0x180029317  mov     [rsp+120h+var_F8], r12
0x18002931c  mov     rax, [rcx]
0x18002931f  mov     [rsp+120h+ppv], rdx
0x180029324  lea     rdx, [rsp+120h+var_E0.data+8]
0x180029329  mov     rax, [rax+50h]
0x18002932d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029332  test    eax, eax
0x180029334  jnz     short loc_180029348
0x180029336  test    r15b, r15b
0x180029339  jz      short loc_180029344
0x18002933b  mov     ecx, [rsp+120h+var_E0.type]
0x18002933f  mov     [r12+rcx*2], ax
0x180029344  xor     ebx, ebx
0x180029346  jmp     short loc_18002934D
0x180029348  mov     ebx, 0Dh
0x18002934d  mov     rcx, rsi; bstrString
0x180029350  call    cs:__imp_SysFreeString
0x180029356  jmp     loc_180029208
0x18002935b  mov     eax, 57h ; 'W'
0x180029360  mov     rcx, [rbp+47h+var_40]
0x180029364  xor     rcx, rsp; StackCookie
0x180029367  call    __security_check_cookie
0x18002936c  mov     rbx, [rsp+120h+arg_10]
0x180029374  add     rsp, 0F0h
0x18002937b  pop     r15
0x18002937d  pop     r14
0x18002937f  pop     r13
0x180029381  pop     r12
0x180029383  pop     rdi
0x180029384  pop     rsi
0x180029385  pop     rbp
0x180029386  retn
```
