# FSDeserializeAttributeArray(uchar *,long,CTUnkArray<IMFAttributes> &)

- ea: `0x18006425c`
- end: `0x1800643cb`
- name: `?FSDeserializeAttributeArray@@YAJPEAEJAEAV?$CTUnkArray@UIMFAttributes@@@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(unsigned int *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083780`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x18000ad10`
- `0x18006425c`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180064310`
- `MFPlat!MFCreateAttributes` at `0x180064310`
- `MFPlat!MFInitAttributesFromBlob` at `0x18006432c`
- `MFPlat!MFInitAttributesFromBlob` at `0x18006432c`

## pseudocode

```c
__int64 __fastcall FSDeserializeAttributeArray(unsigned int *a1, int a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const UINT8 *v7; // rsi
  unsigned int i; // ebp
  HRESULT v9; // eax
  __int64 v10; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+70h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( a2 <= 0 )
    {
      v5 = -2147024809;
      if ( !g_wppLevels )
        return v5;
      v6 = 58;
      goto LABEL_4;
    }
    if ( a1[1] <= a2 )
    {
      v5 = 0;
      v7 = (const UINT8 *)(a1 + 2);
      for ( i = 0; ; ++i )
      {
        if ( i >= *a1 )
          return v5;
        ppMFAttributes = 0;
        v9 = MFCreateAttributes(&ppMFAttributes, 1u);
        v5 = v9;
        if ( v9 < 0 )
          break;
        v9 = MFInitAttributesFromBlob(ppMFAttributes, v7 + 8, *((_DWORD *)v7 + 1));
        v5 = v9;
        if ( v9 < 0 )
        {
          if ( g_wppLevels )
          {
            v10 = 61;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(a3, ppMFAttributes) )
        {
          v5 = -2147024882;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids,
              0,
              -2147024882);
          goto LABEL_24;
        }
        v7 += *((unsigned int *)v7 + 1) + 8;
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      }
      if ( g_wppLevels )
      {
        v10 = 60;
LABEL_23:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids, 0, v9);
      }
LABEL_24:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      return v5;
    }
    v5 = -2147024809;
    if ( g_wppLevels )
    {
      v6 = 59;
      goto LABEL_4;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( g_wppLevels )
    {
      v6 = 57;
LABEL_4:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids,
        0,
        -2147024809);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18006425c  push    rbx
0x18006425e  push    rbp
0x18006425f  push    rsi
0x180064260  push    rdi
0x180064261  push    r14
0x180064263  push    r15
0x180064265  sub     rsp, 38h
0x180064269  mov     r15, r8
0x18006426c  mov     rdi, rcx
0x18006426f  test    rcx, rcx
0x180064272  jnz     short loc_1800642AE
0x180064274  mov     eax, 80070057h
0x180064279  mov     ebx, eax
0x18006427b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064282  jb      loc_1800643BC
0x180064288  lea     edx, [rcx+39h]
0x18006428b  mov     rcx, cs:WPP_GLOBAL_Control
0x180064292  lea     r8, WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids
0x180064299  xor     r9d, r9d
0x18006429c  mov     [rsp+68h+var_48], eax
0x1800642a0  mov     rcx, [rcx+10h]
0x1800642a4  call    WPP_SF_qD
0x1800642a9  jmp     loc_1800643BC
0x1800642ae  test    edx, edx
0x1800642b0  jg      short loc_1800642CD
0x1800642b2  mov     eax, 80070057h
0x1800642b7  mov     ebx, eax
0x1800642b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800642c0  jb      loc_1800643BC
0x1800642c6  mov     edx, 3Ah ; ':'
0x1800642cb  jmp     short loc_18006428B
0x1800642cd  cmp     [rcx+4], edx
0x1800642d0  jbe     short loc_1800642ED
0x1800642d2  mov     eax, 80070057h
0x1800642d7  mov     ebx, eax
0x1800642d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800642e0  jb      loc_1800643BC
0x1800642e6  mov     edx, 3Bh ; ';'
0x1800642eb  jmp     short loc_18006428B
0x1800642ed  xor     ebx, ebx
0x1800642ef  lea     rsi, [rcx+8]
0x1800642f3  xor     ebp, ebp
0x1800642f5  cmp     ebp, [rdi]
0x1800642f7  jnb     loc_1800643BC
0x1800642fd  mov     edx, 1; cInitialSize
0x180064302  mov     [rsp+68h+ppMFAttributes], 0
0x18006430b  lea     rcx, [rsp+68h+ppMFAttributes]; ppMFAttributes
0x180064310  call    cs:__imp_MFCreateAttributes
0x180064316  mov     ebx, eax
0x180064318  test    eax, eax
0x18006431a  js      short loc_180064386
0x18006431c  mov     r8d, [rsi+4]; cbBufSize
0x180064320  lea     r14, [rsi+8]
0x180064324  mov     rcx, [rsp+68h+ppMFAttributes]; pAttributes
0x180064329  mov     rdx, r14; pBuf
0x18006432c  call    cs:__imp_MFInitAttributesFromBlob
0x180064332  mov     ebx, eax
0x180064334  test    eax, eax
0x180064336  js      short loc_180064376
0x180064338  mov     rdx, [rsp+68h+ppMFAttributes]
0x18006433d  mov     rcx, r15
0x180064340  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180064345  test    eax, eax
0x180064347  jz      short loc_18006435D
0x180064349  mov     esi, [rsi+4]
0x18006434c  lea     rcx, [rsp+68h+ppMFAttributes]; void *
0x180064351  add     rsi, r14
0x180064354  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180064359  inc     ebp
0x18006435b  jmp     short loc_1800642F5
0x18006435d  mov     ebx, 8007000Eh
0x180064362  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064369  jb      short loc_1800643B2
0x18006436b  mov     edx, 3Eh ; '>'
0x180064370  mov     [rsp+68h+var_48], ebx
0x180064374  jmp     short loc_180064398
0x180064376  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006437d  jb      short loc_1800643B2
0x18006437f  mov     edx, 3Dh ; '='
0x180064384  jmp     short loc_180064394
0x180064386  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006438d  jb      short loc_1800643B2
0x18006438f  mov     edx, 3Ch ; '<'
0x180064394  mov     [rsp+68h+var_48], eax
0x180064398  mov     rcx, cs:WPP_GLOBAL_Control
0x18006439f  lea     r8, WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids
0x1800643a6  xor     r9d, r9d
0x1800643a9  mov     rcx, [rcx+10h]
0x1800643ad  call    WPP_SF_qD
0x1800643b2  lea     rcx, [rsp+68h+ppMFAttributes]; void *
0x1800643b7  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800643bc  mov     eax, ebx
0x1800643be  add     rsp, 38h
0x1800643c2  pop     r15
0x1800643c4  pop     r14
0x1800643c6  pop     rdi
0x1800643c7  pop     rsi
0x1800643c8  pop     rbp
0x1800643c9  pop     rbx
0x1800643ca  retn
```
