# NgcUtils::NgcContainerKeyName::ParseKeyNameString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800208b0`
- end: `0x180021167`
- name: `?ParseKeyNameString@NgcContainerKeyName@NgcUtils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@11@Z`
- size: `2231`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18001e950`

## callees

- `0x180006750`
- `0x18000a8e0`
- `0x18000c980`
- `0x18000cab0`
- `0x1800208b0`
- `0x180025634`
- `0x180029488`
- `0x18002c240`
- `0x18002c640`
- `0x18002cae0`
- `0x18002cdec`
- `0x18002d500`
- `0x180047a4c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020bfa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020d22`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020ff4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021123`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020bfa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020d22`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180020ff4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021123`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::NgcContainerKeyName::ParseKeyNameString(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rax
  _QWORD *v6; // r14
  char *v7; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  void *v11; // rax
  __int64 v12; // r13
  size_t v13; // r12
  size_t v14; // rbx
  unsigned __int64 v15; // r15
  size_t v16; // rcx
  void *v17; // rax
  char *v18; // r14
  size_t v19; // rbx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  void *v22; // rcx
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdx
  void *v25; // rcx
  char *first_of; // rax
  char *v27; // r14
  unsigned __int64 v28; // rsi
  char *v29; // rax
  unsigned __int64 v30; // rsi
  _QWORD *v31; // rax
  char *v32; // r15
  __int64 v33; // rdx
  void *v34; // r14
  void *v35; // rax
  char *v36; // rax
  void *Src; // [rsp+30h] [rbp-89h] BYREF
  __int64 v39; // [rsp+38h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-79h] BYREF
  __int64 v41; // [rsp+50h] [rbp-69h]
  void *v42[2]; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-51h]
  unsigned __int64 v44; // [rsp+70h] [rbp-49h]
  void *v45[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v46; // [rsp+88h] [rbp-31h]
  unsigned __int64 v47; // [rsp+90h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+98h] [rbp-21h] BYREF
  char *v49; // [rsp+A8h] [rbp-11h]
  int v50; // [rsp+B0h] [rbp-9h]
  int v51; // [rsp+B4h] [rbp-5h]
  void **p_Src; // [rsp+B8h] [rbp-1h]
  __int64 v53; // [rsp+C0h] [rbp+7h]

  *(_QWORD *)&EventDescriptor.Id = a4;
  v41 = a3;
  v39 = a2;
  v5 = a1[2];
  if ( v5 > 0x433 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v39) = -2147024809;
      p_Src = (void **)&v39;
      v53 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v49 = (char *)word_1800AE3DA;
      v50 = 55;
      v51 = 1;
      LODWORD(Src) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_87:
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      return 2147942487LL;
    }
    return 2147942487LL;
  }
  if ( a1[3] <= 7u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  if ( v5 )
  {
    v7 = (char *)v6 + 2 * v5;
    trivial_2 = _std_find_trivial_2(v6, v7, 47);
    if ( (char *)trivial_2 != v7 )
    {
      v9 = (trivial_2 - (__int64)v6) >> 1;
      if ( v9 != -1 )
      {
        *(_OWORD *)v45 = 0;
        v46 = 0;
        v47 = 7;
        LOWORD(v45[0]) = 0;
        *(_OWORD *)v42 = 0;
        v10 = a1[2];
        if ( v10 >= v9 )
          v10 = (trivial_2 - (__int64)v6) >> 1;
        if ( a1[3] <= 7u )
          v11 = a1;
        else
          v11 = (void *)*a1;
        Src = v11;
        v12 = 0x7FFFFFFFFFFFFFFELL;
        if ( v10 > 0x7FFFFFFFFFFFFFFELL )
          goto LABEL_89;
        v13 = -2;
        if ( v10 <= 7 )
        {
          v43 = v10;
          v44 = 7;
          v14 = 2 * v10;
          memcpy_0(v42, v11, v14);
          *(_WORD *)((char *)v42 + v14) = 0;
          goto LABEL_31;
        }
        v15 = v10 | 7;
        if ( (v10 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          if ( v15 < 0xA )
            v15 = 10;
          if ( v15 + 1 > 0x7FFFFFFFFFFFFFFFLL )
            goto LABEL_91;
          v16 = 2 * (v15 + 1);
          if ( !v16 )
          {
            v18 = 0;
LABEL_30:
            v42[0] = v18;
            v43 = v10;
            v44 = v15;
            v19 = 2 * v10;
            memcpy_0(v18, Src, v19);
            *(_WORD *)&v18[v19] = 0;
LABEL_31:
            std::wstring::operator=(v45, v42);
            v20 = v44;
            if ( v44 > 7 )
            {
              v21 = 2 * v44 + 2;
              if ( v21 < 0x1000 )
              {
                v22 = v42[0];
              }
              else
              {
                v22 = (void *)*((_QWORD *)v42[0] - 1);
                if ( (unsigned __int64)((char *)v42[0] - (char *)v22 - 8) > 0x1F )
                  goto LABEL_68;
                v21 = 2 * v44 + 41;
              }
              operator delete(v22, v21);
            }
            v23 = v9 + 1;
            if ( v9 + 1 >= a1[2] )
            {
              if ( (unsigned int)dword_1800BE0B8 > 2 )
              {
                LODWORD(Src) = -2147024809;
                p_Src = &Src;
                v53 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 2;
                EventDescriptor.Keyword = 0;
                UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                UserData.Reserved = 2;
                v49 = &byte_1800AE2A7;
                v50 = 42;
                v51 = 1;
                LODWORD(v39) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
              }
              if ( v47 > 7 )
              {
                v24 = 2 * v47 + 2;
                if ( v24 < 0x1000 )
                {
                  operator delete(v45[0], v24);
                }
                else
                {
                  v25 = (void *)*((_QWORD *)v45[0] - 1);
                  if ( (unsigned __int64)((char *)v45[0] - (char *)v25 - 8) > 0x1F )
                    __fastfail(5u);
                  operator delete(v25, 2 * v47 + 41);
                }
              }
              return 2147942487LL;
            }
            first_of = (char *)std::wstring::find_first_of(a1, v20, v9 + 1);
            v27 = first_of;
            Src = first_of;
            if ( first_of == (char *)-1LL )
            {
              if ( (unsigned int)dword_1800BE0B8 > 2 )
              {
                LODWORD(Src) = -2147024809;
                p_Src = &Src;
                v53 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 2;
                EventDescriptor.Keyword = 0;
                UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                UserData.Reserved = 2;
                v49 = byte_1800AE2DD;
                v50 = 42;
                v51 = 1;
                LODWORD(v39) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
              }
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v45);
              return 2147942487LL;
            }
            *(_OWORD *)v42 = 0;
            v43 = 0;
            v44 = 0;
            v28 = a1[2];
            if ( v28 < v23 )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
              __debugbreak();
            }
            v29 = &first_of[-v23];
            v30 = v28 - v23;
            if ( v30 >= (unsigned __int64)v29 )
              v30 = (unsigned __int64)v29;
            if ( a1[3] <= 7u )
              v31 = a1;
            else
              v31 = (_QWORD *)*a1;
            if ( v30 <= 0x7FFFFFFFFFFFFFFELL )
            {
              v32 = (char *)v31 + 2 * v23;
              if ( v30 <= 7 )
              {
                v43 = v30;
                v44 = 7;
                memcpy_0(v42, v32, 2 * v30);
                *((_WORD *)v42 + v30) = 0;
                v30 = v43;
LABEL_72:
                if ( !v30 || v46 )
                {
                  if ( (unsigned __int64)(v27 + 1) < a1[2] )
                  {
                    if ( std::wstring::find_first_of(a1, v33, v27 + 1) == -1 )
                    {
                      std::wstring::substr(a1, &UserData, v27 + 1, -1);
                      std::wstring::operator=(v39, v45);
                      std::wstring::operator=(v41, v42);
                      std::wstring::operator=(*(_QWORD *)&EventDescriptor.Id, &UserData);
                      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&UserData);
                      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v42);
                      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v45);
                      return 0;
                    }
                    if ( (unsigned int)dword_1800BE0B8 <= 2 )
                      goto LABEL_83;
                    LODWORD(Src) = -2147024809;
                    p_Src = &Src;
                    v53 = 4;
                    *(_DWORD *)&EventDescriptor.Id = 184549376;
                    *(_DWORD *)&EventDescriptor.Level = 2;
                    EventDescriptor.Keyword = 0;
                    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                    v36 = &byte_1800AE277;
                    v50 = 36;
                    goto LABEL_82;
                  }
                  if ( (unsigned int)dword_1800BE0B8 > 2 )
                  {
                    LODWORD(Src) = -2147024809;
                    p_Src = &Src;
                    v53 = 4;
                    *(_DWORD *)&EventDescriptor.Id = 184549376;
                    *(_DWORD *)&EventDescriptor.Level = 2;
                    EventDescriptor.Keyword = 0;
                    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                    v36 = &byte_1800AE237;
                    v50 = 52;
                    goto LABEL_82;
                  }
                }
                else if ( (unsigned int)dword_1800BE0B8 > 2 )
                {
                  LODWORD(Src) = -2147024809;
                  p_Src = &Src;
                  v53 = 4;
                  *(_DWORD *)&EventDescriptor.Id = 184549376;
                  *(_DWORD *)&EventDescriptor.Level = 2;
                  EventDescriptor.Keyword = 0;
                  UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                  UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                  v36 = byte_1800AE313;
                  v50 = 54;
LABEL_82:
                  v49 = v36;
                  UserData.Reserved = 2;
                  v51 = 1;
                  LODWORD(v39) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                  EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
                }
LABEL_83:
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v42);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v45);
                return 2147942487LL;
              }
              if ( (v30 | 7) <= 0x7FFFFFFFFFFFFFFELL )
              {
                v12 = v30 | 7;
                if ( (v30 | 7) < 0xA )
                  v12 = 10;
                if ( (unsigned __int64)(v12 + 1) > 0x7FFFFFFFFFFFFFFFLL )
                  goto LABEL_91;
                v13 = 2 * (v12 + 1);
                if ( !v13 )
                {
                  v34 = 0;
LABEL_71:
                  v42[0] = v34;
                  v43 = v30;
                  v44 = v12;
                  memcpy_0(v34, v32, 2 * v30);
                  *((_WORD *)v34 + v30) = 0;
                  v27 = (char *)Src;
                  goto LABEL_72;
                }
              }
              if ( v13 < 0x1000 )
              {
                v34 = operator new(v13);
                goto LABEL_71;
              }
              if ( v13 + 39 >= v13 )
              {
                v35 = operator new(v13 + 39);
                if ( v35 )
                {
                  v34 = (void *)(((unsigned __int64)v35 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                  *((_QWORD *)v34 - 1) = v35;
                  goto LABEL_71;
                }
LABEL_68:
                __fastfail(5u);
              }
LABEL_91:
              std::_Throw_bad_array_new_length();
            }
LABEL_89:
            std::_Xlen_string();
          }
        }
        else
        {
          v15 = 0x7FFFFFFFFFFFFFFELL;
          v16 = -2;
        }
        if ( v16 < 0x1000 )
        {
          v18 = (char *)operator new(v16);
        }
        else
        {
          if ( v16 + 39 < v16 )
            goto LABEL_91;
          v17 = operator new(v16 + 39);
          if ( !v17 )
            goto LABEL_68;
          v18 = (char *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v18 - 1) = v17;
        }
        goto LABEL_30;
      }
    }
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(Src) = -2147024809;
    p_Src = &Src;
    v53 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
    UserData.Reserved = 2;
    v49 = byte_1800AE41D;
    v50 = 42;
    v51 = 1;
    LODWORD(v39) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    goto LABEL_87;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800208b0  push    rbp
0x1800208b2  push    rbx
0x1800208b3  push    rsi
0x1800208b4  push    rdi
0x1800208b5  push    r12
0x1800208b7  push    r13
0x1800208b9  push    r14
0x1800208bb  push    r15
0x1800208bd  lea     rbp, [rsp-1Fh]
0x1800208c2  sub     rsp, 0D8h
0x1800208c9  mov     rax, cs:__security_cookie
0x1800208d0  xor     rax, rsp
0x1800208d3  mov     [rbp+57h+var_48], rax
0x1800208d7  mov     qword ptr [rbp+57h+EventDescriptor.Id], r9
0x1800208db  mov     [rbp+57h+var_C0], r8
0x1800208df  mov     [rsp+110h+var_D8], rdx
0x1800208e4  mov     rdi, rcx
0x1800208e7  xor     r15d, r15d
0x1800208ea  mov     rax, [rcx+10h]
0x1800208ee  cmp     rax, 433h
0x1800208f4  jbe     loc_180020985
0x1800208fa  mov     eax, cs:dword_1800BE0B8
0x180020900  cmp     eax, 2
0x180020903  jbe     loc_18002112F
0x180020909  mov     dword ptr [rsp+110h+var_D8], 80070057h
0x180020911  lea     rax, [rsp+110h+var_D8]
0x180020916  mov     [rbp+57h+var_58], rax
0x18002091a  mov     [rbp+57h+var_50], 4
0x180020922  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180020929  movzx   eax, cs:word_1800AE3D0
0x180020930  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180020933  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180020937  mov     rax, cs:off_1800BE0C0
0x18002093e  mov     [rbp+57h+var_78.Ptr], rax
0x180020942  movzx   eax, word ptr [rax]
0x180020945  mov     [rbp+57h+var_78.Size], eax
0x180020948  mov     dword ptr [rbp+57h+var_78.0Ch], 2
0x18002094f  lea     rax, word_1800AE3DA
0x180020956  mov     [rbp+57h+var_68], rax
0x18002095a  mov     [rbp+57h+var_60], 37h ; '7'
0x180020961  mov     [rbp+57h+var_5C], 1
0x180020968  lea     rax, _TraceLoggingMetadataEnd
0x18002096f  lea     rcx, _TraceLoggingMetadata
0x180020976  sub     eax, ecx
0x180020978  mov     dword ptr [rsp+110h+Src], eax
0x18002097c  mov     eax, dword ptr [rsp+110h+Src]
0x180020980  jmp     loc_180021101
0x180020985  cmp     qword ptr [rcx+18h], 7
0x18002098a  jbe     short loc_180020991
0x18002098c  mov     r14, [rcx]
0x18002098f  jmp     short loc_180020994
0x180020991  mov     r14, rdi
0x180020994  test    rax, rax
0x180020997  jz      loc_18002107B
0x18002099d  lea     rbx, [r14+rax*2]
0x1800209a1  mov     r8d, 2Fh ; '/'
0x1800209a7  mov     rdx, rbx
0x1800209aa  mov     rcx, r14
0x1800209ad  call    __std_find_trivial_2
0x1800209b2  mov     rsi, rax
0x1800209b5  cmp     rax, rbx
0x1800209b8  jz      loc_18002107B
0x1800209be  sub     rsi, r14
0x1800209c1  sar     rsi, 1
0x1800209c4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800209c8  jz      loc_18002107B
0x1800209ce  xorps   xmm0, xmm0
0x1800209d1  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x1800209d5  mov     [rbp+57h+var_88], r15
0x1800209d9  mov     [rbp+57h+var_80], 7
0x1800209e1  mov     word ptr [rbp+57h+var_98], r15w
0x1800209e6  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1800209ea  mov     rbx, [rdi+10h]
0x1800209ee  cmp     rbx, rsi
0x1800209f1  cmovnb  rbx, rsi
0x1800209f5  cmp     qword ptr [rdi+18h], 7
0x1800209fa  jbe     short loc_180020A01
0x1800209fc  mov     rax, [rdi]
0x1800209ff  jmp     short loc_180020A04
0x180020a01  mov     rax, rdi
0x180020a04  mov     [rsp+110h+Src], rax
0x180020a09  mov     r13, 7FFFFFFFFFFFFFFEh
0x180020a13  cmp     rbx, r13
0x180020a16  ja      loc_180021155
0x180020a1c  mov     ecx, 0Ah
0x180020a21  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180020a2b  mov     r12, 0FFFFFFFFFFFFFFFEh
0x180020a32  cmp     rbx, 7
0x180020a36  ja      short loc_180020A61
0x180020a38  mov     [rbp+57h+var_A8], rbx
0x180020a3c  mov     [rbp+57h+var_A0], 7
0x180020a44  add     rbx, rbx
0x180020a47  mov     r8, rbx; Size
0x180020a4a  mov     rdx, rax; Src
0x180020a4d  lea     rcx, [rbp+57h+var_B8]; void *
0x180020a51  call    memcpy_0
0x180020a56  mov     word ptr [rbp+rbx+57h+var_B8], r15w
0x180020a5c  jmp     loc_180020AF5
0x180020a61  mov     r15, rbx
0x180020a64  or      r15, 7
0x180020a68  cmp     r15, r13
0x180020a6b  jbe     short loc_180020AA8
0x180020a6d  mov     r15, r13
0x180020a70  mov     rcx, r12; Size
0x180020a73  cmp     rcx, 1000h
0x180020a7a  jb      short loc_180020AC6
0x180020a7c  lea     rax, [rcx+27h]
0x180020a80  cmp     rax, rcx
0x180020a83  jbe     loc_180021161
0x180020a89  mov     rcx, rax; Size
0x180020a8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020a91  test    rax, rax
0x180020a94  jz      loc_180020E17
0x180020a9a  lea     r14, [rax+27h]
0x180020a9e  and     r14, 0FFFFFFFFFFFFFFE0h
0x180020aa2  mov     [r14-8], rax
0x180020aa6  jmp     short loc_180020ACE
0x180020aa8  cmp     r15, rcx
0x180020aab  cmovb   r15, rcx
0x180020aaf  lea     rcx, [r15+1]
0x180020ab3  cmp     rcx, rdx
0x180020ab6  ja      loc_180021161
0x180020abc  add     rcx, rcx
0x180020abf  jnz     short loc_180020A73
0x180020ac1  xor     r14d, r14d
0x180020ac4  jmp     short loc_180020ACE
0x180020ac6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020acb  mov     r14, rax
0x180020ace  mov     [rbp+57h+var_B8], r14
0x180020ad2  mov     [rbp+57h+var_A8], rbx
0x180020ad6  mov     [rbp+57h+var_A0], r15
0x180020ada  add     rbx, rbx
0x180020add  mov     r8, rbx; Size
0x180020ae0  mov     rdx, [rsp+110h+Src]; Src
0x180020ae5  mov     rcx, r14; void *
0x180020ae8  call    memcpy_0
0x180020aed  xor     r15d, r15d
0x180020af0  mov     [rbx+r14], r15w
0x180020af5  lea     rdx, [rbp+57h+var_B8]
0x180020af9  lea     rcx, [rbp+57h+var_98]
0x180020afd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020b02  mov     rdx, [rbp+57h+var_A0]
0x180020b06  cmp     rdx, 7
0x180020b0a  jbe     short loc_180020B44
0x180020b0c  mov     rax, [rbp+57h+var_B8]
0x180020b10  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180020b18  cmp     rdx, 1000h
0x180020b1f  jb      short loc_180020B3C
0x180020b21  mov     rcx, [rax-8]
0x180020b25  sub     rax, rcx
0x180020b28  sub     rax, 8
0x180020b2c  cmp     rax, 1Fh
0x180020b30  ja      loc_180020E17
0x180020b36  add     rdx, 27h ; '''
0x180020b3a  jmp     short loc_180020B3F
0x180020b3c  mov     rcx, rax; void *
0x180020b3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b44  lea     rbx, [rsi+1]
0x180020b48  cmp     rbx, [rdi+10h]
0x180020b4c  jb      loc_180020C5D
0x180020b52  mov     eax, cs:dword_1800BE0B8
0x180020b58  cmp     eax, 2
0x180020b5b  jbe     loc_180020C07
0x180020b61  mov     dword ptr [rsp+110h+Src], 80070057h
0x180020b69  lea     rax, [rsp+110h+Src]
0x180020b6e  mov     [rbp+57h+var_58], rax
0x180020b72  mov     [rbp+57h+var_50], 4
0x180020b7a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180020b81  movzx   eax, cs:word_1800AE29D
0x180020b88  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180020b8b  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180020b8f  mov     rax, cs:off_1800BE0C0
0x180020b96  mov     [rbp+57h+var_78.Ptr], rax
0x180020b9a  movzx   eax, word ptr [rax]
0x180020b9d  mov     [rbp+57h+var_78.Size], eax
0x180020ba0  mov     dword ptr [rbp+57h+var_78.0Ch], 2
0x180020ba7  lea     rax, byte_1800AE2A7
0x180020bae  mov     [rbp+57h+var_68], rax
0x180020bb2  mov     [rbp+57h+var_60], 2Ah ; '*'
0x180020bb9  mov     [rbp+57h+var_5C], 1
0x180020bc0  lea     rax, _TraceLoggingMetadataEnd
0x180020bc7  lea     rcx, _TraceLoggingMetadata
0x180020bce  sub     eax, ecx
0x180020bd0  mov     dword ptr [rsp+110h+var_D8], eax
0x180020bd4  mov     eax, dword ptr [rsp+110h+var_D8]
0x180020bd8  lea     rax, [rbp+57h+var_78]
0x180020bdc  mov     [rsp+110h+UserData], rax; UserData
0x180020be1  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x180020be9  xor     r9d, r9d; RelatedActivityId
0x180020bec  xor     r8d, r8d; ActivityId
0x180020bef  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180020bf3  mov     rcx, cs:RegHandle; RegHandle
0x180020bfa  call    cs:__imp_EventWriteTransfer
0x180020c01  nop     dword ptr [rax+rax+00h]
0x180020c06  nop
0x180020c07  mov     rdx, [rbp+57h+var_80]
0x180020c0b  cmp     rdx, 7
0x180020c0f  jbe     loc_18002112F
0x180020c15  mov     rax, [rbp+57h+var_98]
0x180020c19  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180020c21  cmp     rdx, 1000h
0x180020c28  jb      short loc_180020C50
0x180020c2a  mov     rcx, [rax-8]; void *
0x180020c2e  sub     rax, rcx
0x180020c31  sub     rax, 8
0x180020c35  cmp     rax, 1Fh
0x180020c39  ja      short loc_180020C49
0x180020c3b  add     rdx, 27h ; '''; unsigned __int64
0x180020c3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020c44  jmp     loc_18002112F
0x180020c49  mov     ecx, 5
0x180020c4e  int     29h; Win8: RtlFailFast(ecx)
0x180020c50  mov     rcx, rax; void *
0x180020c53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020c58  jmp     loc_18002112F
0x180020c5d  mov     r8, rbx
0x180020c60  mov     rcx, rdi
0x180020c63  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x180020c68  mov     r14, rax
0x180020c6b  mov     [rsp+110h+Src], rax
0x180020c70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020c74  jnz     loc_180020D3D
0x180020c7a  mov     eax, cs:dword_1800BE0B8
0x180020c80  cmp     eax, 2
0x180020c83  jbe     loc_180020D2F
0x180020c89  mov     dword ptr [rsp+110h+Src], 80070057h
0x180020c91  lea     rax, [rsp+110h+Src]
0x180020c96  mov     [rbp+57h+var_58], rax
0x180020c9a  mov     [rbp+57h+var_50], 4
0x180020ca2  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180020ca9  movzx   eax, cs:word_1800AE2D3
0x180020cb0  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180020cb3  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x180020cb7  mov     rax, cs:off_1800BE0C0
0x180020cbe  mov     [rbp+57h+var_78.Ptr], rax
0x180020cc2  movzx   eax, word ptr [rax]
0x180020cc5  mov     [rbp+57h+var_78.Size], eax
0x180020cc8  mov     dword ptr [rbp+57h+var_78.0Ch], 2
0x180020ccf  lea     rax, byte_1800AE2DD
0x180020cd6  mov     [rbp+57h+var_68], rax
0x180020cda  mov     [rbp+57h+var_60], 2Ah ; '*'
0x180020ce1  mov     [rbp+57h+var_5C], 1
0x180020ce8  lea     rax, _TraceLoggingMetadataEnd
0x180020cef  lea     rcx, _TraceLoggingMetadata
0x180020cf6  sub     eax, ecx
0x180020cf8  mov     dword ptr [rsp+110h+var_D8], eax
0x180020cfc  mov     eax, dword ptr [rsp+110h+var_D8]
0x180020d00  lea     rax, [rbp+57h+var_78]
0x180020d04  mov     [rsp+110h+UserData], rax; UserData
0x180020d09  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x180020d11  xor     r9d, r9d; RelatedActivityId
0x180020d14  xor     r8d, r8d; ActivityId
0x180020d17  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180020d1b  mov     rcx, cs:RegHandle; RegHandle
0x180020d22  call    cs:__imp_EventWriteTransfer
0x180020d29  nop     dword ptr [rax+rax+00h]
0x180020d2e  nop
0x180020d2f  lea     rcx, [rbp+57h+var_98]
0x180020d33  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180020d38  jmp     loc_18002112F
0x180020d3d  xorps   xmm0, xmm0
0x180020d40  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180020d44  mov     [rbp+57h+var_A8], r15
0x180020d48  mov     [rbp+57h+var_A0], r15
0x180020d4c  mov     rsi, [rdi+10h]
0x180020d50  cmp     rsi, rbx
0x180020d53  jb      loc_18002115B
0x180020d59  sub     rax, rbx
0x180020d5c  sub     rsi, rbx
0x180020d5f  cmp     rsi, rax
0x180020d62  cmovnb  rsi, rax
0x180020d66  cmp     qword ptr [rdi+18h], 7
0x180020d6b  jbe     short loc_180020D72
0x180020d6d  mov     rax, [rdi]
0x180020d70  jmp     short loc_180020D75
0x180020d72  mov     rax, rdi
0x180020d75  cmp     rsi, r13
0x180020d78  ja      loc_180021155
0x180020d7e  lea     r15, [rax+rbx*2]
0x180020d82  cmp     rsi, 7
0x180020d86  ja      short loc_180020DB9
0x180020d88  mov     [rbp+57h+var_A8], rsi
0x180020d8c  mov     [rbp+57h+var_A0], 7
0x180020d94  lea     rbx, [rsi+rsi]
0x180020d98  mov     r8, rbx; Size
0x180020d9b  mov     rdx, r15; Src
0x180020d9e  lea     rcx, [rbp+57h+var_B8]; void *
0x180020da2  call    memcpy_0
0x180020da7  xor     r15d, r15d
0x180020daa  mov     word ptr [rbp+rbx+57h+var_B8], r15w
0x180020db0  mov     rsi, [rbp+57h+var_A8]
0x180020db4  jmp     loc_180020E62
0x180020db9  mov     rax, rsi
0x180020dbc  or      rax, 7
0x180020dc0  cmp     rax, r13
0x180020dc3  ja      short loc_180020DF6
0x180020dc5  mov     r13, rax
0x180020dc8  cmp     rax, 0Ah
0x180020dcc  mov     eax, 0Ah
0x180020dd1  cmovb   r13, rax
  ... truncated ...
```
