# WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(WindowsPerformanceRecorder::CControlManager *,ushort const *,_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>> const &)

- ea: `0x180001d74`
- end: `0x180001fc0`
- name: `?AddSystemStacks@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAVCControlManager@2@PEBGPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXAEBV?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(__int64, WindowsPerformanceRecorder::CControlManager *, const unsigned __int16 *, struct _TRACE_ENABLE_FLAG_EXT_HEADER *, void *, __int64 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800195b0`
- `0x18003d11c`
- `0x180063aec`

## callees

- `0x180001d74`
- `0x180001fd0`
- `0x180002770`
- `0x18000a0f0`
- `0x180017d70`
- `0x18001e6e0`
- `0x180039de4`
- `0x18004794c`
- `0x18004f964`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001fa7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001fa7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001e29`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001e29`

## string_xrefs

- `0x180001f7a`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(
        __int64 a1,
        WindowsPerformanceRecorder::CControlManager *a2,
        const unsigned __int16 *a3,
        struct _TRACE_ENABLE_FLAG_EXT_HEADER *a4,
        void *a5,
        __int64 **a6)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v8; // rbp
  __int64 i; // rbx
  DWORD v10; // edi
  const struct _OSVERSIONINFOEXW *OSVersionInfo; // rax
  unsigned __int64 v12; // rcx
  __int64 j; // rax
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  unsigned __int64 v16; // r14
  __int64 v17; // rax
  signed int v18; // esi
  const unsigned __int16 *v19; // r13
  int v20; // r12d
  DWORD v21; // edi
  const struct _GUID *v22; // r8
  char *v23; // [rsp+28h] [rbp-80h]
  struct IControlErrorInfo *v24; // [rsp+38h] [rbp-70h]
  _QWORD v25[13]; // [rsp+40h] [rbp-68h] BYREF
  char v30; // [rsp+D8h] [rbp+30h]

  v25[1] = -2;
  v6 = (unsigned __int64)a6[1];
  if ( v6 > WindowsPerformanceRecorder::CSystemProviderElement::GetRunningOSMaximumStackWalkedKernelEventTypes() )
    return 3310895122LL;
  v8 = 0;
  for ( i = **a6; !*(_BYTE *)(i + 25); i = j )
  {
    v10 = *(_DWORD *)(i + 44);
    OSVersionInfo = Performance::COSVersionInfo::GetOSVersionInfo();
    v12 = v8 + 1;
    if ( v10 > OSVersionInfo->dwBuildNumber )
      v12 = v8;
    v8 = v12;
    if ( *(_BYTE *)(*(_QWORD *)(i + 16) + 25LL) )
    {
      for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 25) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        i = j;
    }
    else
    {
      j = std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Min();
    }
  }
  if ( !v8 )
    return 0;
  v14 = malloc(4 * v8);
  v15 = v14;
  v25[2] = v14;
  if ( v14 )
  {
    memset_0(v14, 0, 4 * v8);
    v16 = 0;
    v17 = **a6;
    v25[0] = v17;
    v18 = -984080383;
    while ( !*(_BYTE *)(v17 + 25) )
    {
      v19 = *(const unsigned __int16 **)(v17 + 32);
      v20 = *(unsigned __int16 *)(v17 + 40);
      v21 = *(_DWORD *)(v17 + 44);
      v30 = *(_BYTE *)(v17 + 48);
      if ( v21 <= Performance::COSVersionInfo::GetOSVersionInfo()->dwBuildNumber )
      {
        if ( v16 < v8 )
          v15[v16++] = v20;
      }
      else if ( a2 )
      {
        WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
          a2,
          -984080383,
          v22,
          0,
          a3,
          *(const unsigned __int16 **)(a1 + 320),
          v19,
          v24);
        v24 = (struct IControlErrorInfo *)v19;
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"AddSystemStacks",
          (const char *)0x38F,
          0xC5582001,
          "%ws: %ws, %ws",
          (const char *)a3,
          *(_QWORD *)(a1 + 320));
        if ( v30 )
          goto LABEL_31;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(v25);
      v17 = v25[0];
    }
    v18 = WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(
            a4,
            (unsigned __int64)a5,
            3u,
            v15,
            4 * (unsigned __int16)v8);
    if ( v18 >= 0 )
      v18 = 0;
    else
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"AddSystemStacks",
        (const char *)0x39F,
        v18,
        "COMGUARD",
        v23);
LABEL_31:
    free(v15);
    return (unsigned int)v18;
  }
  else
  {
    free(0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180001d74  mov     rax, rsp
0x180001d77  mov     [rax+20h], r9
0x180001d7b  mov     [rax+18h], r8
0x180001d7f  mov     [rax+10h], rdx
0x180001d83  mov     [rax+8], rcx
0x180001d87  push    rbx
0x180001d88  push    rbp
0x180001d89  push    rsi
0x180001d8a  push    rdi
0x180001d8b  push    r12
0x180001d8d  push    r13
0x180001d8f  push    r14
0x180001d91  push    r15
0x180001d93  sub     rsp, 68h
0x180001d97  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x180001d9f  mov     rsi, [rsp+0A8h+arg_28]
0x180001da7  mov     rbx, [rsi+8]
0x180001dab  call    ?GetRunningOSMaximumStackWalkedKernelEventTypes@CSystemProviderElement@WindowsPerformanceRecorder@@SA_KXZ; WindowsPerformanceRecorder::CSystemProviderElement::GetRunningOSMaximumStackWalkedKernelEventTypes(void)
0x180001db0  cmp     rbx, rax
0x180001db3  jbe     short loc_180001DBF
0x180001db5  mov     eax, 0C5584012h
0x180001dba  jmp     loc_180001FAF
0x180001dbf  xor     ebp, ebp
0x180001dc1  mov     rbx, [rsi]
0x180001dc4  mov     rbx, [rbx]
0x180001dc7  cmp     byte ptr [rbx+19h], 0
0x180001dcb  jnz     short loc_180001E12
0x180001dcd  mov     edi, [rbx+2Ch]
0x180001dd0  call    ?GetOSVersionInfo@COSVersionInfo@Performance@@SAAEBU_OSVERSIONINFOEXW@@XZ; Performance::COSVersionInfo::GetOSVersionInfo(void)
0x180001dd5  lea     rcx, [rbp+1]
0x180001dd9  cmp     edi, [rax+0Ch]
0x180001ddc  cmova   rcx, rbp
0x180001de0  mov     rbp, rcx
0x180001de3  mov     rcx, [rbx+10h]
0x180001de7  cmp     byte ptr [rcx+19h], 0
0x180001deb  jz      short loc_180001E08
0x180001ded  mov     rax, [rbx+8]
0x180001df1  jmp     short loc_180001E00
0x180001df3  cmp     rbx, [rax+10h]
0x180001df7  jnz     short loc_180001E0D
0x180001df9  mov     rbx, rax
0x180001dfc  mov     rax, [rax+8]
0x180001e00  cmp     byte ptr [rax+19h], 0
0x180001e04  jz      short loc_180001DF3
0x180001e06  jmp     short loc_180001E0D
0x180001e08  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@@std@@SAPEAU?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Min(std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *> *)
0x180001e0d  mov     rbx, rax
0x180001e10  jmp     short loc_180001DC7
0x180001e12  test    rbp, rbp
0x180001e15  jnz     short loc_180001E1E
0x180001e17  xor     eax, eax
0x180001e19  jmp     loc_180001FAF
0x180001e1e  lea     r15, ds:0[rbp*4]
0x180001e26  mov     rcx, r15; Size
0x180001e29  call    cs:__imp_malloc
0x180001e2f  mov     rbx, rax
0x180001e32  mov     [rsp+0A8h+var_58], rax
0x180001e37  test    rax, rax
0x180001e3a  jnz     short loc_180001E4E
0x180001e3c  xor     ecx, ecx; Block
0x180001e3e  call    cs:__imp_free
0x180001e44  mov     eax, 8007000Eh
0x180001e49  jmp     loc_180001FAF
0x180001e4e  mov     r8, r15; Size
0x180001e51  xor     edx, edx; Val
0x180001e53  mov     rcx, rbx; void *
0x180001e56  call    memset_0
0x180001e5b  xor     r14d, r14d
0x180001e5e  mov     rax, [rsi]
0x180001e61  mov     rax, [rax]
0x180001e64  mov     [rsp+0A8h+var_68], rax
0x180001e69  mov     esi, 0C5582001h
0x180001e6e  cmp     byte ptr [rax+19h], 0
0x180001e72  jnz     loc_180001F50
0x180001e78  mov     r13, [rax+20h]
0x180001e7c  movzx   r12d, word ptr [rax+28h]
0x180001e81  mov     edi, [rax+2Ch]
0x180001e84  mov     al, [rax+30h]
0x180001e87  mov     byte ptr [rsp+0A8h+arg_28], al
0x180001e8e  call    ?GetOSVersionInfo@COSVersionInfo@Performance@@SAAEBU_OSVERSIONINFOEXW@@XZ; Performance::COSVersionInfo::GetOSVersionInfo(void)
0x180001e93  cmp     edi, [rax+0Ch]
0x180001e96  jbe     loc_180001F30
0x180001e9c  mov     rdi, [rsp+0A8h+arg_8]
0x180001ea4  test    rdi, rdi
0x180001ea7  jz      loc_180001F3C
0x180001ead  mov     [rsp+0A8h+var_78], r13; unsigned __int16 *
0x180001eb2  mov     rax, [rsp+0A8h+arg_0]
0x180001eba  mov     rax, [rax+140h]
0x180001ec1  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180001ec6  mov     r12, [rsp+0A8h+arg_10]
0x180001ece  mov     [rsp+0A8h+Format], r12; unsigned __int16 *
0x180001ed3  xor     r9d, r9d; struct _GUID *
0x180001ed6  mov     edx, esi; int
0x180001ed8  mov     rcx, rdi; this
0x180001edb  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x180001ee0  mov     [rsp+0A8h+var_70], r13
0x180001ee5  mov     rax, [rsp+0A8h+arg_0]
0x180001eed  mov     rax, [rax+140h]
0x180001ef4  mov     [rsp+0A8h+var_78], rax
0x180001ef9  mov     [rsp+0A8h+var_80], r12; char *
0x180001efe  lea     rax, aWsWsWs; "%ws: %ws, %ws"
0x180001f05  mov     [rsp+0A8h+Format], rax; Format
0x180001f0a  mov     r9d, esi; unsigned int
0x180001f0d  mov     r8d, 38Fh; char *
0x180001f13  lea     rdx, aAddsystemstack; "AddSystemStacks"
0x180001f1a  mov     ecx, 3; this
0x180001f1f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180001f24  cmp     byte ptr [rsp+0A8h+arg_28], 0
0x180001f2c  jz      short loc_180001F3C
0x180001f2e  jmp     short loc_180001FA4
0x180001f30  cmp     r14, rbp
0x180001f33  jnb     short loc_180001F3C
0x180001f35  mov     [rbx+r14*4], r12d
0x180001f39  inc     r14
0x180001f3c  lea     rcx, [rsp+0A8h+var_68]
0x180001f41  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(void)
0x180001f46  mov     rax, [rsp+0A8h+var_68]
0x180001f4b  jmp     loc_180001E6E
0x180001f50  mov     r8d, 3; unsigned __int16
0x180001f56  mov     word ptr [rsp+0A8h+Format], r15w; unsigned __int16
0x180001f5c  mov     r9, rbx; void *
0x180001f5f  mov     rdx, [rsp+0A8h+arg_20]; void *
0x180001f67  mov     rcx, [rsp+0A8h+arg_18]; struct _TRACE_ENABLE_FLAG_EXT_HEADER *
0x180001f6f  call    ?AddExtendedFlagEntry@CETWProperties@WindowsPerformanceRecorder@@CAJPEAU_TRACE_ENABLE_FLAG_EXT_HEADER@@PEBXG1G@Z; WindowsPerformanceRecorder::CETWProperties::AddExtendedFlagEntry(_TRACE_ENABLE_FLAG_EXT_HEADER *,void const *,ushort,void const *,ushort)
0x180001f74  mov     esi, eax
0x180001f76  test    eax, eax
0x180001f78  jns     short loc_180001FA2
0x180001f7a  lea     rax, aComguard; "COMGUARD"
0x180001f81  mov     [rsp+0A8h+Format], rax; Format
0x180001f86  mov     r9d, esi; unsigned int
0x180001f89  mov     r8d, 39Fh; char *
0x180001f8f  lea     rdx, aAddsystemstack; "AddSystemStacks"
0x180001f96  mov     ecx, 2; this
0x180001f9b  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180001fa0  jmp     short loc_180001FA4
0x180001fa2  xor     esi, esi
0x180001fa4  mov     rcx, rbx; Block
0x180001fa7  call    cs:__imp_free
0x180001fad  mov     eax, esi
0x180001faf  add     rsp, 68h
0x180001fb3  pop     r15
0x180001fb5  pop     r14
0x180001fb7  pop     r13
0x180001fb9  pop     r12
0x180001fbb  pop     rdi
0x180001fbc  pop     rsi
0x180001fbd  pop     rbp
0x180001fbe  pop     rbx
0x180001fbf  retn
```
