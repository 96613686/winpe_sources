# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria &)

- ea: `0x18002cccc`
- end: `0x18002cf56`
- name: `?Matches@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV12@@Z`
- size: `650`
- prototype: `bool __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *__hidden this, struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180018e84`
- `0x18002a964`
- `0x18002ad54`

## callees

- `0x1800156e4`
- `0x18002cccc`
- `0x18002cf5c`
- `0x18002d640`

## pseudocode

```c
bool __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *this,
        struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *a2)
{
  __int64 v4; // r9
  const wchar_t *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rcx
  const wchar_t *v8; // rdx
  size_t v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  const wchar_t *v13; // r9
  size_t v14; // r8
  __int16 v15; // ax
  __int16 v16; // cx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  const wchar_t *v20; // rax
  size_t v21; // r8
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  bool result; // al
  __int64 v25; // rcx
  __int64 v26; // rdx
  size_t v27; // r8
  __int64 v28; // rax
  __int64 v29; // rcx
  const wchar_t *v30; // rdx
  __int64 v31; // rax
  size_t v32; // r8
  __int64 v33; // rcx
  __int64 v34; // rdx
  size_t v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rdx

  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(this);
  v4 = *(_QWORD *)a2;
  v5 = &S1;
  if ( *(_QWORD *)a2 )
  {
    v6 = *(_QWORD *)this;
    if ( *(_QWORD *)this )
    {
      v7 = *(unsigned int *)(v6 + 4);
      v8 = *(const wchar_t **)(v6 + 16);
    }
    else
    {
      v7 = 0;
      v8 = &S1;
    }
    v9 = *(unsigned int *)(v4 + 4);
    if ( v9 == v7 && (!*(_DWORD *)(v4 + 4) || !wmemcmp(*(const wchar_t **)(v4 + 16), v8, v9)) )
      return 1;
  }
  v10 = *((_QWORD *)a2 + 1);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 1);
    if ( v11 )
    {
      v12 = *(unsigned int *)(v11 + 4);
      v13 = *(const wchar_t **)(v11 + 16);
    }
    else
    {
      v12 = 0;
      v13 = &S1;
    }
    v14 = *(unsigned int *)(v10 + 4);
    if ( v14 == v12 && (!*(_DWORD *)(v10 + 4) || !wmemcmp(*(const wchar_t **)(v10 + 16), v13, v14)) )
      return 1;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetImpl'::`2'::impl) )
  {
    v15 = *((_WORD *)a2 + 8);
    if ( v15 )
    {
      v16 = *((_WORD *)a2 + 9);
      if ( v16 )
      {
        if ( v15 == *((_WORD *)this + 8) && v16 == *((_WORD *)this + 9) )
        {
          v17 = *((_QWORD *)a2 + 3);
          if ( v17 )
          {
            v18 = *((_QWORD *)this + 3);
            if ( !v18 )
            {
              v19 = 0;
              v20 = &S1;
              goto LABEL_26;
            }
LABEL_25:
            v19 = *(unsigned int *)(v18 + 4);
            v20 = *(const wchar_t **)(v18 + 16);
            if ( !v17 )
            {
              v21 = 0;
LABEL_28:
              if ( v21 == v19 )
              {
                if ( v21 )
                {
                  v22 = v20;
                  v23 = v5;
                  return wmemcmp(v23, v22, v21) == 0;
                }
                return 1;
              }
              return 0;
            }
LABEL_26:
            v21 = *(unsigned int *)(v17 + 4);
            v5 = *(const wchar_t **)(v17 + 16);
            goto LABEL_28;
          }
          if ( *((_QWORD *)this + 3) )
          {
            v18 = *((_QWORD *)this + 3);
            goto LABEL_25;
          }
          return 1;
        }
      }
    }
  }
  v25 = *((_QWORD *)a2 + 4);
  if ( v25 )
  {
    if ( *((_QWORD *)a2 + 5) )
    {
      v26 = *((_QWORD *)this + 4);
      if ( v26 )
      {
        if ( *((_QWORD *)this + 5) )
        {
          v27 = *(unsigned int *)(v25 + 4);
          if ( v27 == *(_DWORD *)(v26 + 4)
            && (!*(_DWORD *)(v25 + 4) || !wmemcmp(*(const wchar_t **)(v25 + 16), *(const wchar_t **)(v26 + 16), v27)) )
          {
            v28 = *((_QWORD *)this + 5);
            if ( v28 )
            {
              v29 = *(unsigned int *)(v28 + 4);
              v30 = *(const wchar_t **)(v28 + 16);
            }
            else
            {
              v29 = 0;
              v30 = &S1;
            }
            v31 = *((_QWORD *)a2 + 5);
            if ( v31 )
            {
              v32 = *(unsigned int *)(v31 + 4);
              v5 = *(const wchar_t **)(v31 + 16);
            }
            else
            {
              v32 = 0;
            }
            if ( v32 == v29 && (!v32 || !wmemcmp(v5, v30, v32)) )
              return 1;
          }
          return 0;
        }
      }
    }
  }
  v33 = *((_QWORD *)a2 + 6);
  if ( v33 && (v34 = *((_QWORD *)this + 6)) != 0 && *((_WORD *)a2 + 28) && *((_WORD *)this + 28) )
  {
    v35 = *(unsigned int *)(v33 + 4);
    if ( v35 != *(_DWORD *)(v34 + 4)
      || *(_DWORD *)(v33 + 4) && wmemcmp(*(const wchar_t **)(v33 + 16), *(const wchar_t **)(v34 + 16), v35) )
    {
      return 0;
    }
    result = 1;
    if ( *((_WORD *)a2 + 28) != *((_WORD *)this + 28) )
      return 0;
  }
  else
  {
    v36 = *((_QWORD *)a2 + 8);
    if ( v36 && (v37 = *((_QWORD *)this + 8)) != 0
      || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetImpl'::`2'::impl)
      && (v36 = *((_QWORD *)a2 + 9)) != 0
      && (v37 = *((_QWORD *)this + 9)) != 0 )
    {
      v21 = *(unsigned int *)(v36 + 4);
      if ( v21 == *(_DWORD *)(v37 + 4) )
      {
        if ( *(_DWORD *)(v36 + 4) )
        {
          v22 = *(const wchar_t **)(v37 + 16);
          v23 = *(const wchar_t **)(v36 + 16);
          return wmemcmp(v23, v22, v21) == 0;
        }
        return 1;
      }
      return 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002cccc  push    rbx
0x18002ccce  push    rbp
0x18002cccf  push    rsi
0x18002ccd0  push    rdi
0x18002ccd1  sub     rsp, 28h
0x18002ccd5  mov     rdi, rdx
0x18002ccd8  mov     rbx, rcx
0x18002ccdb  call    ?Normalize@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAAXXZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(void)
0x18002cce0  mov     r9, [rdi]
0x18002cce3  lea     rsi, S1
0x18002ccea  xor     ebp, ebp
0x18002ccec  test    r9, r9
0x18002ccef  jz      short loc_18002CD2B
0x18002ccf1  mov     rax, [rbx]
0x18002ccf4  test    rax, rax
0x18002ccf7  jz      short loc_18002CD02
0x18002ccf9  mov     ecx, [rax+4]
0x18002ccfc  mov     rdx, [rax+10h]
0x18002cd00  jmp     short loc_18002CD08
0x18002cd02  mov     rcx, rbp
0x18002cd05  mov     rdx, rsi; S2
0x18002cd08  mov     r8d, [r9+4]; N
0x18002cd0c  cmp     r8, rcx
0x18002cd0f  jnz     short loc_18002CD2B
0x18002cd11  test    r8, r8
0x18002cd14  jz      loc_18002CE04
0x18002cd1a  mov     rcx, [r9+10h]; S1
0x18002cd1e  call    wmemcmp
0x18002cd23  test    eax, eax
0x18002cd25  jz      loc_18002CE04
0x18002cd2b  mov     rcx, [rdi+8]
0x18002cd2f  test    rcx, rcx
0x18002cd32  jz      short loc_18002CD72
0x18002cd34  mov     rax, [rbx+8]
0x18002cd38  test    rax, rax
0x18002cd3b  jz      short loc_18002CD46
0x18002cd3d  mov     edx, [rax+4]
0x18002cd40  mov     r9, [rax+10h]
0x18002cd44  jmp     short loc_18002CD4C
0x18002cd46  mov     rdx, rbp
0x18002cd49  mov     r9, rsi
0x18002cd4c  mov     r8d, [rcx+4]; N
0x18002cd50  cmp     r8, rdx
0x18002cd53  jnz     short loc_18002CD72
0x18002cd55  test    r8, r8
0x18002cd58  jz      loc_18002CE04
0x18002cd5e  mov     rcx, [rcx+10h]; S1
0x18002cd62  mov     rdx, r9; S2
0x18002cd65  call    wmemcmp
0x18002cd6a  test    eax, eax
0x18002cd6c  jz      loc_18002CE04
0x18002cd72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetImpl(void)'::`2'::impl
0x18002cd79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::__private_IsEnabled(void)
0x18002cd7e  test    al, al
0x18002cd80  jnz     loc_18002CE0B
0x18002cd86  movzx   eax, word ptr [rdi+10h]
0x18002cd8a  test    ax, ax
0x18002cd8d  jz      short loc_18002CE0B
0x18002cd8f  movzx   ecx, word ptr [rdi+12h]
0x18002cd93  test    cx, cx
0x18002cd96  jz      short loc_18002CE0B
0x18002cd98  cmp     ax, [rbx+10h]
0x18002cd9c  jnz     short loc_18002CE0B
0x18002cd9e  cmp     cx, [rbx+12h]
0x18002cda2  jnz     short loc_18002CE0B
0x18002cda4  mov     rcx, [rdi+18h]
0x18002cda8  test    rcx, rcx
0x18002cdab  jz      short loc_18002CDBE
0x18002cdad  mov     rax, [rbx+18h]
0x18002cdb1  test    rax, rax
0x18002cdb4  jnz     short loc_18002CDC8
0x18002cdb6  mov     rdx, rbp
0x18002cdb9  mov     rax, rsi
0x18002cdbc  jmp     short loc_18002CDD4
0x18002cdbe  cmp     [rbx+18h], rbp
0x18002cdc2  jz      short loc_18002CE04
0x18002cdc4  mov     rax, [rbx+18h]
0x18002cdc8  mov     edx, [rax+4]
0x18002cdcb  mov     rax, [rax+10h]
0x18002cdcf  test    rcx, rcx
0x18002cdd2  jz      short loc_18002CDDE
0x18002cdd4  mov     r8d, [rcx+4]
0x18002cdd8  mov     rsi, [rcx+10h]
0x18002cddc  jmp     short loc_18002CDE1
0x18002cdde  mov     r8, rbp; N
0x18002cde1  cmp     r8, rdx
0x18002cde4  jnz     loc_18002CE9F
0x18002cdea  test    r8, r8
0x18002cded  jz      short loc_18002CE04
0x18002cdef  mov     rdx, rax; S2
0x18002cdf2  mov     rcx, rsi; S1
0x18002cdf5  call    wmemcmp
0x18002cdfa  test    eax, eax
0x18002cdfc  setz    al
0x18002cdff  jmp     loc_18002CF4D
0x18002ce04  mov     al, 1
0x18002ce06  jmp     loc_18002CF4D
0x18002ce0b  mov     rcx, [rdi+20h]
0x18002ce0f  test    rcx, rcx
0x18002ce12  jz      loc_18002CEA7
0x18002ce18  cmp     [rdi+28h], rbp
0x18002ce1c  jz      loc_18002CEA7
0x18002ce22  mov     rdx, [rbx+20h]
0x18002ce26  test    rdx, rdx
0x18002ce29  jz      short loc_18002CEA7
0x18002ce2b  cmp     [rbx+28h], rbp
0x18002ce2f  jz      short loc_18002CEA7
0x18002ce31  mov     r8d, [rcx+4]; N
0x18002ce35  mov     eax, [rdx+4]
0x18002ce38  cmp     r8, rax
0x18002ce3b  jnz     short loc_18002CE9F
0x18002ce3d  test    r8, r8
0x18002ce40  jz      short loc_18002CE53
0x18002ce42  mov     rdx, [rdx+10h]; S2
0x18002ce46  mov     rcx, [rcx+10h]; S1
0x18002ce4a  call    wmemcmp
0x18002ce4f  test    eax, eax
0x18002ce51  jnz     short loc_18002CE9F
0x18002ce53  mov     rax, [rbx+28h]
0x18002ce57  test    rax, rax
0x18002ce5a  jz      short loc_18002CE65
0x18002ce5c  mov     ecx, [rax+4]
0x18002ce5f  mov     rdx, [rax+10h]
0x18002ce63  jmp     short loc_18002CE6B
0x18002ce65  mov     rcx, rbp
0x18002ce68  mov     rdx, rsi; S2
0x18002ce6b  mov     rax, [rdi+28h]
0x18002ce6f  test    rax, rax
0x18002ce72  jz      short loc_18002CE7E
0x18002ce74  mov     r8d, [rax+4]
0x18002ce78  mov     rsi, [rax+10h]
0x18002ce7c  jmp     short loc_18002CE81
0x18002ce7e  mov     r8, rbp; N
0x18002ce81  cmp     r8, rcx
0x18002ce84  jnz     short loc_18002CE9F
0x18002ce86  test    r8, r8
0x18002ce89  jz      loc_18002CE04
0x18002ce8f  mov     rcx, rsi; S1
0x18002ce92  call    wmemcmp
0x18002ce97  test    eax, eax
0x18002ce99  jz      loc_18002CE04
0x18002ce9f  mov     al, bpl
0x18002cea2  jmp     loc_18002CF4D
0x18002cea7  mov     rcx, [rdi+30h]
0x18002ceab  test    rcx, rcx
0x18002ceae  jz      short loc_18002CEF5
0x18002ceb0  mov     rdx, [rbx+30h]
0x18002ceb4  test    rdx, rdx
0x18002ceb7  jz      short loc_18002CEF5
0x18002ceb9  cmp     [rdi+38h], bp
0x18002cebd  jbe     short loc_18002CEF5
0x18002cebf  cmp     [rbx+38h], bp
0x18002cec3  jbe     short loc_18002CEF5
0x18002cec5  mov     r8d, [rcx+4]; N
0x18002cec9  mov     eax, [rdx+4]
0x18002cecc  cmp     r8, rax
0x18002cecf  jnz     short loc_18002CE9F
0x18002ced1  test    r8, r8
0x18002ced4  jz      short loc_18002CEE7
0x18002ced6  mov     rdx, [rdx+10h]; S2
0x18002ceda  mov     rcx, [rcx+10h]; S1
0x18002cede  call    wmemcmp
0x18002cee3  test    eax, eax
0x18002cee5  jnz     short loc_18002CE9F
0x18002cee7  movzx   eax, word ptr [rbx+38h]
0x18002ceeb  cmp     [rdi+38h], ax
0x18002ceef  mov     al, 1
0x18002cef1  jz      short loc_18002CF4D
0x18002cef3  jmp     short loc_18002CE9F
0x18002cef5  mov     rcx, [rdi+40h]
0x18002cef9  test    rcx, rcx
0x18002cefc  jz      short loc_18002CF29
0x18002cefe  mov     rdx, [rbx+40h]
0x18002cf02  test    rdx, rdx
0x18002cf05  jz      short loc_18002CF29
0x18002cf07  mov     r8d, [rcx+4]
0x18002cf0b  mov     eax, [rdx+4]
0x18002cf0e  cmp     r8, rax
0x18002cf11  jnz     short loc_18002CE9F
0x18002cf13  test    r8, r8
0x18002cf16  jz      loc_18002CE04
0x18002cf1c  mov     rdx, [rdx+10h]
0x18002cf20  mov     rcx, [rcx+10h]
0x18002cf24  jmp     loc_18002CDF5
0x18002cf29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::GetImpl(void)'::`2'::impl
0x18002cf30  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2USBDeviceMatch>::__private_IsEnabled(void)
0x18002cf35  test    al, al
0x18002cf37  jnz     short loc_18002CF4B
0x18002cf39  mov     rcx, [rdi+48h]
0x18002cf3d  test    rcx, rcx
0x18002cf40  jz      short loc_18002CF4B
0x18002cf42  mov     rdx, [rbx+48h]
0x18002cf46  test    rdx, rdx
0x18002cf49  jnz     short loc_18002CF07
0x18002cf4b  xor     al, al
0x18002cf4d  add     rsp, 28h
0x18002cf51  pop     rdi
0x18002cf52  pop     rsi
0x18002cf53  pop     rbp
0x18002cf54  pop     rbx
0x18002cf55  retn
```
