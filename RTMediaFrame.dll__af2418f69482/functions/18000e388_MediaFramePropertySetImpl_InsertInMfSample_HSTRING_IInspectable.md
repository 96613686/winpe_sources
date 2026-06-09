# MediaFramePropertySetImpl::InsertInMfSample(HSTRING__ *,IInspectable *)

- ea: `0x18000e388`
- end: `0x18000e737`
- name: `?InsertInMfSample@MediaFramePropertySetImpl@@AEAAXPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `943`
- prototype: `void(MediaFramePropertySetImpl *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e178`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000e388`
- `0x180026920`
- `0x18003a320`
- `0x18003a5d0`
- `0x18003b498`
- `0x18003b4dc`
- `0x18003b524`
- `0x18003b880`
- `0x18003b8d0`
- `0x18003b914`
- `0x18003bcb0`
- `0x18003bcf8`
- `0x18003bd40`
- `0x18003bd84`
- `0x18003bdc8`
- `0x18003dc90`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e6b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e70d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e6b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e70d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e3cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e6e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e3cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e6e9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000e3d8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000e3d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MediaFramePropertySetImpl::InsertInMfSample(
        MediaFramePropertySetImpl *this,
        HSTRING a2,
        struct IInspectable *a3)
{
  const OLECHAR *StringRawBuffer; // rax
  HSTRING v6; // rbx
  int v7; // esi
  unsigned int Type; // eax
  int v9; // edx
  unsigned int Double; // eax
  int v11; // edx
  unsigned int v12; // eax
  int v13; // edx
  unsigned int Int64; // eax
  int v15; // edx
  unsigned int Int32; // eax
  int v17; // edx
  __int64 v18; // r8
  unsigned int Boolean; // eax
  int v20; // edx
  unsigned __int64 v21; // rcx
  unsigned int UInt8Array; // eax
  int v23; // edx
  unsigned int v24; // ebx
  unsigned int Guid; // eax
  int v26; // edx
  unsigned int Inspectable; // eax
  int v28; // edx
  unsigned int v29; // eax
  int v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, IID *, PCWSTR); // rbx
  PCWSTR v35; // rax
  unsigned int v36; // eax
  int v37; // edx
  unsigned __int8 v38[8]; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  int v40; // [rsp+40h] [rbp-29h]
  HSTRING v41; // [rsp+48h] [rbp-21h] BYREF
  int v42; // [rsp+50h] [rbp-19h]
  int v43; // [rsp+58h] [rbp-11h] BYREF
  HSTRING v44; // [rsp+60h] [rbp-9h] BYREF
  int v45; // [rsp+68h] [rbp-1h]
  LPVOID pv[2]; // [rsp+70h] [rbp+7h] BYREF
  IID iid; // [rsp+80h] [rbp+17h] BYREF

  if ( *((_QWORD *)this + 12) )
  {
    iid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    if ( IIDFromString(StringRawBuffer, &iid) >= 0 )
    {
      RoVariant::RoVariant((RoVariant *)&v44, a3, 0, 0);
      v43 = 0;
      v6 = v44;
      pv[0] = v44;
      v7 = v45;
      LODWORD(pv[1]) = v45;
      Type = RoVariant::Accessor::get_Type((RoVariant::Accessor *)pv, (enum Windows::Foundation::PropertyType *)&v43);
      MF::ThrowIfFailed((MF *)Type, v9);
      if ( v43 <= 11 )
      {
        if ( v43 == 11 )
        {
          v38[0] = 0;
          pv[0] = v6;
          LODWORD(pv[1]) = v7;
          Boolean = RoVariant::Accessor::GetBoolean((RoVariant::Accessor *)pv, v38);
          MF::ThrowIfFailed((MF *)Boolean, v20);
          v18 = v38[0];
        }
        else
        {
          if ( v43 == 4 )
          {
            LODWORD(string) = 0;
            pv[0] = v6;
            LODWORD(pv[1]) = v7;
            Int32 = RoVariant::Accessor::GetInt32((RoVariant::Accessor *)pv, (int *)&string);
          }
          else
          {
            if ( v43 != 5 )
            {
              if ( v43 == 6 )
              {
                pv[0] = 0;
                string = v6;
                v40 = v7;
                Int64 = RoVariant::Accessor::GetInt64((RoVariant::Accessor *)&string, (__int64 *)pv);
              }
              else
              {
                if ( v43 != 7 )
                {
                  if ( v43 == 9 )
                  {
                    pv[0] = 0;
                    string = v6;
                    v40 = v7;
                    Double = RoVariant::Accessor::GetDouble((RoVariant::Accessor *)&string, (double *)pv);
                    MF::ThrowIfFailed((MF *)Double, v11);
                    v12 = (*(__int64 (__fastcall **)(_QWORD, IID *))(**((_QWORD **)this + 12) + 184LL))(
                            *((_QWORD *)this + 12),
                            &iid);
LABEL_19:
                    v21 = v12;
LABEL_26:
                    MF::ThrowIfFailed((MF *)v21, v13);
                  }
LABEL_32:
                  RoVariant::~RoVariant((RoVariant *)&v44);
                  return;
                }
                pv[0] = 0;
                string = v6;
                v40 = v7;
                Int64 = RoVariant::Accessor::GetUInt64((RoVariant::Accessor *)&string, (unsigned __int64 *)pv);
              }
              goto LABEL_13;
            }
            LODWORD(string) = 0;
            pv[0] = v6;
            LODWORD(pv[1]) = v7;
            Int32 = RoVariant::Accessor::GetUInt32((RoVariant::Accessor *)pv, (unsigned int *)&string);
          }
          MF::ThrowIfFailed((MF *)Int32, v17);
          v18 = (unsigned int)string;
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD, IID *, __int64))(**((_QWORD **)this + 12) + 168LL))(
                *((_QWORD *)this + 12),
                &iid,
                v18);
        goto LABEL_19;
      }
      if ( v43 == 12 )
      {
        v41 = v6;
        v42 = v7;
        WindowsDeleteString(0);
        string = 0;
        v31 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v41, &string);
        MF::ThrowIfFailed((MF *)v31, v32);
        v33 = *((_QWORD *)this + 12);
        v34 = *(__int64 (__fastcall **)(__int64, IID *, PCWSTR))(*(_QWORD *)v33 + 200LL);
        v35 = WindowsGetStringRawBuffer(string, 0);
        v36 = v34(v33, &iid, v35);
        MF::ThrowIfFailed((MF *)v36, v37);
        WindowsDeleteString(string);
        goto LABEL_32;
      }
      if ( v43 == 13 )
      {
        string = 0;
        v41 = v6;
        v42 = v7;
        Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&string);
        Inspectable = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v41, (struct IInspectable **)&string);
        MF::ThrowIfFailed((MF *)Inspectable, v28);
        v29 = (*(__int64 (__fastcall **)(_QWORD, IID *, HSTRING))(**((_QWORD **)this + 12) + 216LL))(
                *((_QWORD *)this + 12),
                &iid,
                string);
        MF::ThrowIfFailed((MF *)v29, v30);
        Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&string);
        goto LABEL_32;
      }
      if ( v43 != 15 )
      {
        if ( v43 == 16 )
        {
          *(_OWORD *)pv = 0;
          v41 = v6;
          v42 = v7;
          Guid = RoVariant::Accessor::GetGuid((RoVariant::Accessor *)&v41, (struct _GUID *)pv);
          MF::ThrowIfFailed((MF *)Guid, v26);
          v12 = (*(__int64 (__fastcall **)(_QWORD, IID *, LPVOID *))(**((_QWORD **)this + 12) + 192LL))(
                  *((_QWORD *)this + 12),
                  &iid,
                  pv);
          goto LABEL_19;
        }
        if ( v43 == 1025 )
        {
          LODWORD(string) = 0;
          pv[0] = 0;
          v41 = v6;
          v42 = v7;
          UInt8Array = RoVariant::Accessor::GetUInt8Array(
                         (RoVariant::Accessor *)&v41,
                         (unsigned int *)&string,
                         (unsigned __int8 **)pv);
          MF::ThrowIfFailed((MF *)UInt8Array, v23);
          v24 = (*(__int64 (__fastcall **)(_QWORD, IID *, LPVOID, _QWORD))(**((_QWORD **)this + 12) + 208LL))(
                  *((_QWORD *)this + 12),
                  &iid,
                  pv[0],
                  (unsigned int)string);
          CoTaskMemFree(pv[0]);
          v21 = v24;
          goto LABEL_26;
        }
        goto LABEL_32;
      }
      pv[0] = 0;
      v41 = v6;
      v42 = v7;
      Int64 = RoVariant::Accessor::GetTimeSpan((RoVariant::Accessor *)&v41, (struct Windows::Foundation::TimeSpan *)pv);
LABEL_13:
      MF::ThrowIfFailed((MF *)Int64, v15);
      v12 = (*(__int64 (__fastcall **)(_QWORD, IID *, LPVOID))(**((_QWORD **)this + 12) + 176LL))(
              *((_QWORD *)this + 12),
              &iid,
              pv[0]);
      goto LABEL_19;
    }
  }
}

```

## disassembly

```asm
0x18000e388  push    rbp
0x18000e38a  push    rbx
0x18000e38b  push    rsi
0x18000e38c  push    rdi
0x18000e38d  push    r14
0x18000e38f  lea     rbp, [rsp-37h]
0x18000e394  sub     rsp, 0A0h
0x18000e39b  mov     rax, cs:__security_cookie
0x18000e3a2  xor     rax, rsp
0x18000e3a5  mov     [rbp+57h+var_30], rax
0x18000e3a9  mov     rbx, r8
0x18000e3ac  mov     rax, rdx
0x18000e3af  mov     rdi, rcx
0x18000e3b2  xor     r14d, r14d
0x18000e3b5  cmp     [rcx+60h], r14
0x18000e3b9  jz      loc_18000E71D
0x18000e3bf  xorps   xmm0, xmm0
0x18000e3c2  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18000e3c6  xor     edx, edx; length
0x18000e3c8  mov     rcx, rax; string
0x18000e3cb  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e3d1  mov     rcx, rax; lpsz
0x18000e3d4  lea     rdx, [rbp+57h+iid]; lpiid
0x18000e3d8  call    cs:__imp_IIDFromString
0x18000e3de  test    eax, eax
0x18000e3e0  js      loc_18000E71D
0x18000e3e6  xor     r9d, r9d; bool
0x18000e3e9  xor     r8d, r8d; bool
0x18000e3ec  mov     rdx, rbx; struct IInspectable *
0x18000e3ef  lea     rcx, [rbp+57h+var_60]; this
0x18000e3f3  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18000e3f8  nop
0x18000e3f9  mov     [rbp+57h+var_68], r14d
0x18000e3fd  mov     rbx, [rbp+57h+var_60]
0x18000e401  mov     [rbp+57h+pv], rbx
0x18000e405  mov     esi, [rbp+57h+var_58]
0x18000e408  mov     dword ptr [rbp+57h+pv+8], esi
0x18000e40b  lea     rdx, [rbp+57h+var_68]; enum Windows::Foundation::PropertyType *
0x18000e40f  lea     rcx, [rbp+57h+pv]; this
0x18000e413  call    ?get_Type@Accessor@RoVariant@@QEBAJPEAW4PropertyType@Foundation@Windows@@@Z; RoVariant::Accessor::get_Type(Windows::Foundation::PropertyType *)
0x18000e418  mov     ecx, eax; this
0x18000e41a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e41f  mov     ecx, [rbp+57h+var_68]
0x18000e422  cmp     ecx, 0Bh
0x18000e425  jg      loc_18000E56B
0x18000e42b  jz      loc_18000E529
0x18000e431  sub     ecx, 4
0x18000e434  jz      loc_18000E50F
0x18000e43a  sub     ecx, 1
0x18000e43d  jz      loc_18000E4EA
0x18000e443  sub     ecx, 1
0x18000e446  jz      short loc_18000E4B4
0x18000e448  sub     ecx, 1
0x18000e44b  jz      short loc_18000E49A
0x18000e44d  cmp     ecx, 2
0x18000e450  jnz     loc_18000E714
0x18000e456  xorps   xmm0, xmm0
0x18000e459  movsd   [rbp+57h+pv], xmm0
0x18000e45e  mov     [rbp+57h+string], rbx
0x18000e462  mov     [rbp+57h+var_80], esi
0x18000e465  lea     rdx, [rbp+57h+pv]; double *
0x18000e469  lea     rcx, [rbp+57h+string]; this
0x18000e46d  call    ?GetDouble@Accessor@RoVariant@@QEBAJPEAN@Z; RoVariant::Accessor::GetDouble(double *)
0x18000e472  mov     ecx, eax; this
0x18000e474  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e479  mov     rcx, [rdi+60h]
0x18000e47d  mov     rax, [rcx]
0x18000e480  movsd   xmm2, [rbp+57h+pv]
0x18000e485  lea     rdx, [rbp+57h+iid]
0x18000e489  mov     rax, [rax+0B8h]
0x18000e490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e495  jmp     loc_18000E564
0x18000e49a  mov     [rbp+57h+pv], r14
0x18000e49e  mov     [rbp+57h+string], rbx
0x18000e4a2  mov     [rbp+57h+var_80], esi
0x18000e4a5  lea     rdx, [rbp+57h+pv]; unsigned __int64 *
0x18000e4a9  lea     rcx, [rbp+57h+string]; this
0x18000e4ad  call    ?GetUInt64@Accessor@RoVariant@@QEBAJPEA_K@Z; RoVariant::Accessor::GetUInt64(unsigned __int64 *)
0x18000e4b2  jmp     short loc_18000E4CC
0x18000e4b4  mov     [rbp+57h+pv], r14
0x18000e4b8  mov     [rbp+57h+string], rbx
0x18000e4bc  mov     [rbp+57h+var_80], esi
0x18000e4bf  lea     rdx, [rbp+57h+pv]; __int64 *
0x18000e4c3  lea     rcx, [rbp+57h+string]; this
0x18000e4c7  call    ?GetInt64@Accessor@RoVariant@@QEBAJPEA_J@Z; RoVariant::Accessor::GetInt64(__int64 *)
0x18000e4cc  mov     ecx, eax; this
0x18000e4ce  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e4d3  mov     rcx, [rdi+60h]
0x18000e4d7  mov     rax, [rcx]
0x18000e4da  mov     r8, [rbp+57h+pv]
0x18000e4de  mov     rax, [rax+0B0h]
0x18000e4e5  jmp     loc_18000E629
0x18000e4ea  mov     dword ptr [rbp+57h+string], r14d
0x18000e4ee  mov     [rbp+57h+pv], rbx
0x18000e4f2  mov     dword ptr [rbp+57h+pv+8], esi
0x18000e4f5  lea     rdx, [rbp+57h+string]; unsigned int *
0x18000e4f9  lea     rcx, [rbp+57h+pv]; this
0x18000e4fd  call    ?GetUInt32@Accessor@RoVariant@@QEBAJPEAI@Z; RoVariant::Accessor::GetUInt32(uint *)
0x18000e502  mov     ecx, eax; this
0x18000e504  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e509  mov     r8d, dword ptr [rbp+57h+string]
0x18000e50d  jmp     short loc_18000E54D
0x18000e50f  mov     dword ptr [rbp+57h+string], r14d
0x18000e513  mov     [rbp+57h+pv], rbx
0x18000e517  mov     dword ptr [rbp+57h+pv+8], esi
0x18000e51a  lea     rdx, [rbp+57h+string]; int *
0x18000e51e  lea     rcx, [rbp+57h+pv]; this
0x18000e522  call    ?GetInt32@Accessor@RoVariant@@QEBAJPEAH@Z; RoVariant::Accessor::GetInt32(int *)
0x18000e527  jmp     short loc_18000E502
0x18000e529  mov     [rbp+57h+var_90], r14b
0x18000e52d  mov     [rbp+57h+pv], rbx
0x18000e531  mov     dword ptr [rbp+57h+pv+8], esi
0x18000e534  lea     rdx, [rbp+57h+var_90]; unsigned __int8 *
0x18000e538  lea     rcx, [rbp+57h+pv]; this
0x18000e53c  call    ?GetBoolean@Accessor@RoVariant@@QEBAJPEAE@Z; RoVariant::Accessor::GetBoolean(uchar *)
0x18000e541  mov     ecx, eax; this
0x18000e543  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e548  movzx   r8d, [rbp+57h+var_90]
0x18000e54d  mov     rcx, [rdi+60h]
0x18000e551  mov     rax, [rcx]
0x18000e554  lea     rdx, [rbp+57h+iid]
0x18000e558  mov     rax, [rax+0A8h]
0x18000e55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e564  mov     ecx, eax
0x18000e566  jmp     loc_18000E5EB
0x18000e56b  sub     ecx, 0Ch
0x18000e56e  jz      loc_18000E6AA
0x18000e574  sub     ecx, 1
0x18000e577  jz      loc_18000E654
0x18000e57d  sub     ecx, 2
0x18000e580  jz      loc_18000E637
0x18000e586  sub     ecx, 1
0x18000e589  jz      short loc_18000E5F5
0x18000e58b  cmp     ecx, 3F1h
0x18000e591  jnz     loc_18000E714
0x18000e597  mov     dword ptr [rbp+57h+string], r14d
0x18000e59b  mov     [rbp+57h+pv], r14
0x18000e59f  mov     [rbp+57h+var_78], rbx
0x18000e5a3  mov     [rbp+57h+var_70], esi
0x18000e5a6  lea     r8, [rbp+57h+pv]; unsigned __int8 **
0x18000e5aa  lea     rdx, [rbp+57h+string]; unsigned int *
0x18000e5ae  lea     rcx, [rbp+57h+var_78]; this
0x18000e5b2  call    ?GetUInt8Array@Accessor@RoVariant@@QEBAJPEAIPEAPEAE@Z; RoVariant::Accessor::GetUInt8Array(uint *,uchar * *)
0x18000e5b7  mov     ecx, eax; this
0x18000e5b9  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e5be  mov     rcx, [rdi+60h]
0x18000e5c2  mov     rax, [rcx]
0x18000e5c5  mov     r9d, dword ptr [rbp+57h+string]
0x18000e5c9  mov     r8, [rbp+57h+pv]
0x18000e5cd  lea     rdx, [rbp+57h+iid]
0x18000e5d1  mov     rax, [rax+0D0h]
0x18000e5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5dd  mov     ebx, eax
0x18000e5df  mov     rcx, [rbp+57h+pv]; pv
0x18000e5e3  call    cs:__imp_CoTaskMemFree
0x18000e5e9  mov     ecx, ebx; this
0x18000e5eb  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e5f0  jmp     loc_18000E714
0x18000e5f5  xorps   xmm0, xmm0
0x18000e5f8  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18000e5fc  mov     [rbp+57h+var_78], rbx
0x18000e600  mov     [rbp+57h+var_70], esi
0x18000e603  lea     rdx, [rbp+57h+pv]; struct _GUID *
0x18000e607  lea     rcx, [rbp+57h+var_78]; this
0x18000e60b  call    ?GetGuid@Accessor@RoVariant@@QEBAJPEAU_GUID@@@Z; RoVariant::Accessor::GetGuid(_GUID *)
0x18000e610  mov     ecx, eax; this
0x18000e612  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e617  mov     rcx, [rdi+60h]
0x18000e61b  mov     rax, [rcx]
0x18000e61e  lea     r8, [rbp+57h+pv]
0x18000e622  mov     rax, [rax+0C0h]
0x18000e629  lea     rdx, [rbp+57h+iid]
0x18000e62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e632  jmp     loc_18000E564
0x18000e637  mov     [rbp+57h+pv], r14
0x18000e63b  mov     [rbp+57h+var_78], rbx
0x18000e63f  mov     [rbp+57h+var_70], esi
0x18000e642  lea     rdx, [rbp+57h+pv]; struct Windows::Foundation::TimeSpan *
0x18000e646  lea     rcx, [rbp+57h+var_78]; this
0x18000e64a  call    ?GetTimeSpan@Accessor@RoVariant@@QEBAJPEAUTimeSpan@Foundation@Windows@@@Z; RoVariant::Accessor::GetTimeSpan(Windows::Foundation::TimeSpan *)
0x18000e64f  jmp     loc_18000E4CC
0x18000e654  mov     [rbp+57h+string], r14
0x18000e658  mov     [rbp+57h+var_78], rbx
0x18000e65c  mov     [rbp+57h+var_70], esi
0x18000e65f  lea     rcx, [rbp+57h+string]
0x18000e663  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e668  lea     rdx, [rbp+57h+string]; struct IInspectable **
0x18000e66c  lea     rcx, [rbp+57h+var_78]; this
0x18000e670  call    ?GetInspectable@Accessor@RoVariant@@QEBAJPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectable(IInspectable * *)
0x18000e675  mov     ecx, eax; this
0x18000e677  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e67c  mov     rcx, [rdi+60h]
0x18000e680  mov     rax, [rcx]
0x18000e683  mov     r8, [rbp+57h+string]
0x18000e687  lea     rdx, [rbp+57h+iid]
0x18000e68b  mov     rax, [rax+0D8h]
0x18000e692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e697  mov     ecx, eax; this
0x18000e699  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e69e  nop
0x18000e69f  lea     rcx, [rbp+57h+string]
0x18000e6a3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e6a8  jmp     short loc_18000E714
0x18000e6aa  mov     [rbp+57h+string], r14
0x18000e6ae  mov     [rbp+57h+var_78], rbx
0x18000e6b2  mov     [rbp+57h+var_70], esi
0x18000e6b5  xor     ecx, ecx; string
0x18000e6b7  call    cs:__imp_WindowsDeleteString
0x18000e6bd  mov     [rbp+57h+string], r14
0x18000e6c1  lea     rdx, [rbp+57h+string]; HSTRING *
0x18000e6c5  lea     rcx, [rbp+57h+var_78]; this
0x18000e6c9  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18000e6ce  mov     ecx, eax; this
0x18000e6d0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e6d5  mov     rdi, [rdi+60h]
0x18000e6d9  mov     rax, [rdi]
0x18000e6dc  mov     rbx, [rax+0C8h]
0x18000e6e3  xor     edx, edx; length
0x18000e6e5  mov     rcx, [rbp+57h+string]; string
0x18000e6e9  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e6ef  mov     r8, rax
0x18000e6f2  lea     rdx, [rbp+57h+iid]
0x18000e6f6  mov     rcx, rdi
0x18000e6f9  mov     rax, rbx
0x18000e6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e701  mov     ecx, eax; this
0x18000e703  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e708  nop
0x18000e709  mov     rcx, [rbp+57h+string]; string
0x18000e70d  call    cs:__imp_WindowsDeleteString
0x18000e713  nop
0x18000e714  lea     rcx, [rbp+57h+var_60]; this
0x18000e718  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18000e71d  mov     rcx, [rbp+57h+var_30]
0x18000e721  xor     rcx, rsp; StackCookie
0x18000e724  call    __security_check_cookie
0x18000e729  add     rsp, 0A0h
0x18000e730  pop     r14
0x18000e732  pop     rdi
0x18000e733  pop     rsi
0x18000e734  pop     rbx
0x18000e735  pop     rbp
0x18000e736  retn
```
