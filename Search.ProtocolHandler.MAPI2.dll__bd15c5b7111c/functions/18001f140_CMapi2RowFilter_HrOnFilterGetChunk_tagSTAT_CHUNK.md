# CMapi2RowFilter::HrOnFilterGetChunk(tagSTAT_CHUNK *)

- ea: `0x18001f140`
- end: `0x18001f39f`
- name: `?HrOnFilterGetChunk@CMapi2RowFilter@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(LCID *this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002300`
- `0x18000835c`
- `0x180013f10`
- `0x180014420`
- `0x180014448`
- `0x1800144b4`
- `0x1800144fc`
- `0x180015144`
- `0x180015778`
- `0x18001579c`
- `0x180017870`
- `0x180017940`
- `0x18001f140`
- `0x180021e5c`
- `0x180021f94`
- `0x180021ff4`
- `0x18003a060`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001f1e1`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18001f1e1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f364`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f364`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f192`

## pseudocode

```c
__int64 __fastcall CMapi2RowFilter::HrOnFilterGetChunk(LCID *this, struct tagSTAT_CHUNK *a2)
{
  _WORD *v4; // rax
  unsigned int v5; // ebx
  LCID SystemDefaultLCID; // eax
  struct CMapi2Property *v8; // rdx
  LCID v9; // eax
  const FILETIME *v10; // rbx
  LCID v11; // eax
  _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-2058h] BYREF
  _BYTE v13[8]; // [rsp+30h] [rbp-2048h] BYREF
  __int64 v14; // [rsp+38h] [rbp-2040h]
  wil::details::in1diag3 *retaddr; // [rsp+2078h] [rbp+0h]

  if ( this[5944] || !(unsigned int)CMapi2RowFilter::FHasAttachment((CMapi2RowFilter *)this) )
  {
    if ( *(_QWORD *)CTPtrSListIterator<CMapi2Property>::operator++(this + 5972) )
    {
      v8 = *(struct CMapi2Property **)CTPtrSListIterator<CMapi2Property>::GetCurrentValue();
      if ( v8 )
        return CMapi2RowFilter::SetValueChunkFromProperty((CMapi2RowFilter *)this, v8, a2);
    }
    if ( this[3237] )
    {
      CLMString::operator=(this + 4, this + 3232);
      this[2060] = 0;
      this[2061] = this[3237];
      *((_BYTE *)this + 8272) = this[2068] & 0xFC | 1;
      v9 = this[5420];
      a2->attribute.guidPropSet.Data1 = -1222250192;
      *(_DWORD *)&a2->attribute.guidPropSet.Data2 = 270157807;
      *(_DWORD *)a2->attribute.guidPropSet.Data4 = 1610805669;
      *(_DWORD *)&a2->attribute.guidPropSet.Data4[4] = -1393844596;
      a2->attribute.psProperty.ulKind = 1;
      LODWORD(a2->attribute.psProperty.propid) = 19;
      a2->breakType = CHUNK_EOS;
      a2->flags = CHUNK_TEXT;
      a2->locale = v9;
      TLMString<4096,4096,4294967295>::TLMString<4096,4096,4294967295>(v13, &byte_1800444C0);
      CLMString::operator=(this + 3232, v14);
      TLMString<4096,4096,4294967295>::~TLMString<4096,4096,4294967295>(v13);
    }
    else
    {
      if ( !*(_QWORD *)CTPtrSListIterator<CLinkWithTime>::operator++(this + 5988) )
        return 2147751680LL;
      v10 = *(const FILETIME **)CTPtrSListIterator<CLinkWithTime>::GetCurrentValue();
      v11 = this[5420];
      a2->attribute.guidPropSet = GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04;
      a2->attribute.psProperty.ulKind = 1;
      LODWORD(a2->attribute.psProperty.propid) = 12;
      a2->breakType = CHUNK_EOS;
      a2->flags = CHUNK_VALUE;
      a2->locale = v11;
      SystemTime = 0;
      FileTimeToSystemTime(v10 + 52, &SystemTime);
      IFilterImpl<CMapi2RowFilter>::SetValueChunkAsLinkWithTime(this, v10);
    }
    return 0;
  }
  ++this[5944];
  v4 = CoTaskMemAlloc(0x18u);
  *(_QWORD *)&SystemTime.wYear = v4;
  if ( v4 )
  {
    *v4 = 11;
    v4[4] = -1;
    IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(this, &SystemTime);
    SystemDefaultLCID = GetSystemDefaultLCID();
    a2->attribute.guidPropSet = GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04;
    a2->attribute.psProperty.ulKind = 1;
    LODWORD(a2->attribute.psProperty.propid) = 23;
    a2->breakType = CHUNK_EOS;
    a2->flags = CHUNK_VALUE;
    a2->locale = SystemDefaultLCID;
    v5 = 0;
  }
  else
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x510,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssph\\mapi2\\mapi2rowfilt.cxx",
      (const char *)0x8007000ELL,
      0);
  }
  wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &SystemTime,
    0);
  return v5;
}

```

## disassembly

```asm
0x18001f140  mov     [rsp+arg_10], rbx
0x18001f145  push    rbp
0x18001f146  push    rsi
0x18001f147  push    rdi
0x18001f148  mov     eax, 2060h
0x18001f14d  call    _alloca_probe
0x18001f152  sub     rsp, rax
0x18001f155  mov     rax, cs:__security_cookie
0x18001f15c  xor     rax, rsp
0x18001f15f  mov     [rsp+2078h+var_28], rax
0x18001f167  mov     rdi, rdx
0x18001f16a  mov     rsi, rcx
0x18001f16d  cmp     dword ptr [rcx+5CE0h], 0
0x18001f174  jnz     loc_18001F227
0x18001f17a  call    ?FHasAttachment@CMapi2RowFilter@@QEAAHXZ; CMapi2RowFilter::FHasAttachment(void)
0x18001f17f  test    eax, eax
0x18001f181  jz      loc_18001F227
0x18001f187  inc     dword ptr [rsi+5CE0h]
0x18001f18d  mov     ecx, 18h; cb
0x18001f192  call    cs:__imp_CoTaskMemAlloc
0x18001f198  mov     qword ptr [rsp+2078h+SystemTime.wYear], rax; int
0x18001f19d  test    rax, rax
0x18001f1a0  jnz     short loc_18001F1C5
0x18001f1a2  mov     rcx, [rsp+2078h]; this
0x18001f1aa  mov     ebx, 8007000Eh
0x18001f1af  mov     r9d, ebx; char *
0x18001f1b2  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18001f1b9  mov     edx, 510h; void *
0x18001f1be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1c3  jmp     short loc_18001F214
0x18001f1c5  mov     ecx, 0Bh
0x18001f1ca  mov     [rax], cx
0x18001f1cd  or      ecx, 0FFFFFFFFh
0x18001f1d0  mov     [rax+8], cx
0x18001f1d4  lea     rdx, [rsp+2078h+SystemTime]
0x18001f1d9  mov     rcx, rsi
0x18001f1dc  call    ?SetValueChunkAsPropvariantAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2DirFilter@@@@IEAAXAEAV?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18001f1e1  call    cs:__imp_GetSystemDefaultLCID
0x18001f1e7  movups  xmm0, xmmword ptr cs:_GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data1
0x18001f1ee  movdqu  xmmword ptr [rdi+10h], xmm0
0x18001f1f3  mov     dword ptr [rdi+20h], 1
0x18001f1fa  mov     dword ptr [rdi+28h], 17h
0x18001f201  mov     dword ptr [rdi+4], 2
0x18001f208  mov     dword ptr [rdi+8], 2
0x18001f20f  mov     [rdi+0Ch], eax
0x18001f212  xor     ebx, ebx
0x18001f214  xor     edx, edx
0x18001f216  lea     rcx, [rsp+2078h+SystemTime]
0x18001f21b  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x18001f220  mov     eax, ebx
0x18001f222  jmp     loc_18001F37C
0x18001f227  lea     rcx, [rsi+5D50h]
0x18001f22e  call    ??E?$CTPtrSListIterator@VCMapi2Property@@@@QEAAAEAPEAVCMapi2Property@@XZ; CTPtrSListIterator<CMapi2Property>::operator++(void)
0x18001f233  cmp     qword ptr [rax], 0
0x18001f237  jz      short loc_18001F256
0x18001f239  call    ?GetCurrentValue@?$CTPtrSListIterator@VCMapi2Property@@@@QEAAAEAPEAVCMapi2Property@@XZ; CTPtrSListIterator<CMapi2Property>::GetCurrentValue(void)
0x18001f23e  mov     rdx, [rax]; struct CMapi2Property *
0x18001f241  test    rdx, rdx
0x18001f244  jz      short loc_18001F256
0x18001f246  mov     r8, rdi; struct tagSTAT_CHUNK *
0x18001f249  mov     rcx, rsi; this
0x18001f24c  call    ?SetValueChunkFromProperty@CMapi2RowFilter@@AEAAJPEAVCMapi2Property@@PEAUtagSTAT_CHUNK@@@Z; CMapi2RowFilter::SetValueChunkFromProperty(CMapi2Property *,tagSTAT_CHUNK *)
0x18001f251  jmp     loc_18001F37C
0x18001f256  lea     rbp, [rsi+3280h]
0x18001f25d  cmp     dword ptr [rbp+14h], 0
0x18001f261  jbe     loc_18001F305
0x18001f267  mov     rdx, rbp
0x18001f26a  lea     rcx, [rsi+10h]
0x18001f26e  call    ??4CLMString@@QEAAXAEBV0@@Z; CLMString::operator=(CLMString const &)
0x18001f273  mov     dword ptr [rsi+2030h], 0
0x18001f27d  mov     eax, [rbp+14h]
0x18001f280  mov     [rsi+2034h], eax
0x18001f286  mov     al, [rsi+2050h]
0x18001f28c  and     al, 0FDh
0x18001f28e  or      al, 1
0x18001f290  mov     [rsi+2050h], al
0x18001f296  mov     eax, [rsi+54B0h]
0x18001f29c  mov     dword ptr [rdi+10h], 0B725F130h
0x18001f2a3  mov     dword ptr [rdi+14h], 101A47EFh
0x18001f2aa  mov     dword ptr [rdi+18h], 6002F1A5h
0x18001f2b1  mov     dword ptr [rdi+1Ch], 0ACEB9E8Ch
0x18001f2b8  mov     dword ptr [rdi+20h], 1
0x18001f2bf  mov     dword ptr [rdi+28h], 13h
0x18001f2c6  mov     dword ptr [rdi+4], 2
0x18001f2cd  mov     dword ptr [rdi+8], 1
0x18001f2d4  mov     [rdi+0Ch], eax
0x18001f2d7  lea     rdx, byte_1800444C0
0x18001f2de  lea     rcx, [rsp+2078h+var_2048]
0x18001f2e3  call    ??0?$TLMString@$0BAAA@$0BAAA@$0PPPPPPPP@@@QEAA@PEBD@Z; TLMString<4096,4096,4294967295>::TLMString<4096,4096,4294967295>(char const *)
0x18001f2e8  nop
0x18001f2e9  mov     rdx, [rsp+2078h+var_2040]
0x18001f2ee  mov     rcx, rbp
0x18001f2f1  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001f2f6  nop
0x18001f2f7  lea     rcx, [rsp+2078h+var_2048]
0x18001f2fc  call    ??1?$TLMString@$0BAAA@$0BAAA@$0PPPPPPPP@@@UEAA@XZ; TLMString<4096,4096,4294967295>::~TLMString<4096,4096,4294967295>(void)
0x18001f301  xor     eax, eax
0x18001f303  jmp     short loc_18001F37C
0x18001f305  lea     rcx, [rsi+5D90h]
0x18001f30c  call    ??E?$CTPtrSListIterator@VCLinkWithTime@@@@QEAAAEAPEAVCLinkWithTime@@XZ; CTPtrSListIterator<CLinkWithTime>::operator++(void)
0x18001f311  cmp     qword ptr [rax], 0
0x18001f315  jz      short loc_18001F377
0x18001f317  call    ?GetCurrentValue@?$CTPtrSListIterator@VCLinkWithTime@@@@QEAAAEAPEAVCLinkWithTime@@XZ; CTPtrSListIterator<CLinkWithTime>::GetCurrentValue(void)
0x18001f31c  mov     rbx, [rax]
0x18001f31f  mov     eax, [rsi+54B0h]
0x18001f325  movups  xmm0, xmmword ptr cs:_GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data1
0x18001f32c  movdqu  xmmword ptr [rdi+10h], xmm0
0x18001f331  mov     dword ptr [rdi+20h], 1
0x18001f338  mov     dword ptr [rdi+28h], 0Ch
0x18001f33f  mov     dword ptr [rdi+4], 2
0x18001f346  mov     dword ptr [rdi+8], 2
0x18001f34d  mov     [rdi+0Ch], eax
0x18001f350  xorps   xmm0, xmm0
0x18001f353  movups  xmmword ptr [rsp+2078h+SystemTime.wYear], xmm0
0x18001f358  lea     rcx, [rbx+1A0h]; lpFileTime
0x18001f35f  lea     rdx, [rsp+2078h+SystemTime]; lpSystemTime
0x18001f364  call    cs:__imp_FileTimeToSystemTime
0x18001f36a  mov     rdx, rbx
0x18001f36d  mov     rcx, rsi
0x18001f370  call    ?SetValueChunkAsLinkWithTime@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXPEAVCLinkWithTime@@@Z; IFilterImpl<CMapi2RowFilter>::SetValueChunkAsLinkWithTime(CLinkWithTime *)
0x18001f375  jmp     short loc_18001F301
0x18001f377  mov     eax, 80041700h
0x18001f37c  mov     rcx, [rsp+2078h+var_28]
0x18001f384  xor     rcx, rsp; StackCookie
0x18001f387  call    __security_check_cookie
0x18001f38c  mov     rbx, [rsp+2078h+arg_10]
0x18001f394  add     rsp, 2060h
0x18001f39b  pop     rdi
0x18001f39c  pop     rsi
0x18001f39d  pop     rbp
0x18001f39e  retn
```
