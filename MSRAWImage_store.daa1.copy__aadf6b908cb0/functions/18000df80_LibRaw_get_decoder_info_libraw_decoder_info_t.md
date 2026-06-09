# LibRaw::get_decoder_info(libraw_decoder_info_t *)

- ea: `0x18000df80`
- end: `0x18000e776`
- name: `?get_decoder_info@LibRaw@@UEAAHPEAUlibraw_decoder_info_t@@@Z`
- size: `2038`
- prototype: `__int64 __fastcall(LibRaw *__hidden this, struct libraw_decoder_info_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df80`

## string_xrefs

- `0x18000e031`: `fuji_compressed_load_raw()`
- `0x18000e332`: `broadcom_load_raw()`
- `0x18000e6d1`: `uncompressed_fp_dng_load_raw()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LibRaw::get_decoder_info(LibRaw *this, struct libraw_decoder_info_t *a2)
{
  void (__fastcall *v3)(LibRaw *__hidden); // rax

  if ( !a2 )
    return 0xFFFFFFFFLL;
  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 2) = 0;
  v3 = (void (__fastcall *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
  if ( !v3 )
    return 4294967292LL;
  if ( v3 == LibRaw::android_tight_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "android_tight_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::android_loose_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "android_loose_load_raw()";
    return 0;
  }
  else if ( (char *)v3 == (char *)LibRaw::vc5_dng_load_raw_placeholder )
  {
    *((_DWORD *)a2 + 2) = 0x4000;
    *(_QWORD *)a2 = "vc5_dng_load_raw_placeholder()";
    return 0;
  }
  else if ( v3 == LibRaw::canon_600_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "canon_600_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::fuji_compressed_load_raw )
  {
    *(_QWORD *)a2 = "fuji_compressed_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::fuji_14bit_load_raw )
  {
    *(_QWORD *)a2 = "fuji_14bit_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::canon_load_raw )
  {
    *(_QWORD *)a2 = "canon_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::lossless_jpeg_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65616;
    *(_QWORD *)a2 = "lossless_jpeg_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::canon_sraw_load_raw )
  {
    *((_DWORD *)a2 + 2) = 0x10000;
    *(_QWORD *)a2 = "canon_sraw_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::crxLoadRaw )
  {
    *(_QWORD *)a2 = "crxLoadRaw()";
    return 0;
  }
  else if ( v3 == LibRaw::lossless_dng_load_raw )
  {
    *((_DWORD *)a2 + 2) = 66128;
    *(_QWORD *)a2 = "lossless_dng_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::packed_dng_load_raw )
  {
    *((_DWORD *)a2 + 2) = 66128;
    *(_QWORD *)a2 = "packed_dng_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::pentax_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65600;
    *(_QWORD *)a2 = "pentax_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65616;
    *(_QWORD *)a2 = "nikon_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_coolscan_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "nikon_coolscan_load_raw()";
    return 0;
  }
  else if ( (char *)v3 == (char *)LibRaw::nikon_he_load_raw_placeholder )
  {
    *((_DWORD *)a2 + 2) = 0x4000;
    *(_QWORD *)a2 = "nikon_he_load_raw_placeholder()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_load_sraw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "nikon_load_sraw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_yuv_load_raw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "nikon_load_yuv_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::rollei_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "rollei_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::phase_one_load_raw )
  {
    *(_QWORD *)a2 = "phase_one_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::phase_one_load_raw_c )
  {
    *((_DWORD *)a2 + 2) = 0x10000;
    *(_QWORD *)a2 = "phase_one_load_raw_c()";
    return 0;
  }
  else if ( v3 == LibRaw::phase_one_load_raw_s )
  {
    *(_QWORD *)a2 = "phase_one_load_raw_s()";
    return 0;
  }
  else if ( v3 == LibRaw::hasselblad_load_raw )
  {
    *((_DWORD *)a2 + 2) = 0x10000;
    *(_QWORD *)a2 = "hasselblad_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::leaf_hdr_load_raw )
  {
    *(_QWORD *)a2 = "leaf_hdr_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::unpacked_load_raw )
  {
    *((_DWORD *)a2 + 2) = 4096;
    *(_QWORD *)a2 = "unpacked_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::unpacked_load_raw_reversed )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "unpacked_load_raw_reversed()";
    return 0;
  }
  else if ( v3 == LibRaw::sinar_4shot_load_raw )
  {
    *((_DWORD *)a2 + 2) = 2048;
    *(_QWORD *)a2 = "sinar_4shot_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::imacon_full_load_raw )
  {
    *(_QWORD *)a2 = "imacon_full_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::hasselblad_full_load_raw )
  {
    *(_QWORD *)a2 = "hasselblad_full_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::packed_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65600;
    *(_QWORD *)a2 = "packed_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::broadcom_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "broadcom_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nokia_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "nokia_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::panasonic_load_raw )
  {
    *((_DWORD *)a2 + 2) = 64;
    *(_QWORD *)a2 = "panasonic_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::panasonicC6_load_raw )
  {
    *(_QWORD *)a2 = "panasonicC6_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::panasonicC7_load_raw )
  {
    *(_QWORD *)a2 = "panasonicC7_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::olympus_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65600;
    *(_QWORD *)a2 = "olympus_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::minolta_rd175_load_raw )
  {
    *(_QWORD *)a2 = "minolta_rd175_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::quicktake_100_load_raw )
  {
    *(_QWORD *)a2 = "quicktake_100_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_radc_load_raw )
  {
    *(_QWORD *)a2 = "kodak_radc_load_raw()";
    return 0;
  }
  else if ( (char *)v3 == (char *)guard_check_icall_nop )
  {
    *(_QWORD *)a2 = "kodak_jpeg_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_dc120_load_raw )
  {
    *(_QWORD *)a2 = "kodak_dc120_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::eight_bit_load_raw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "eight_bit_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_c330_load_raw || v3 == LibRaw::kodak_c603_load_raw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "kodak_yrgb_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_262_load_raw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "kodak_262_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_65000_load_raw )
  {
    *((_DWORD *)a2 + 2) = 16;
    *(_QWORD *)a2 = "kodak_65000_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_ycbcr_load_raw )
  {
    *((_DWORD *)a2 + 2) = 272;
    *(_QWORD *)a2 = "kodak_ycbcr_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::kodak_rgb_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "kodak_rgb_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::sony_load_raw )
  {
    *(_QWORD *)a2 = "sony_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::sony_ljpeg_load_raw )
  {
    *(_QWORD *)a2 = "sony_ljpeg_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::sony_arw_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65600;
    *(_QWORD *)a2 = "sony_arw_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::sony_arw2_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65648;
    *(_QWORD *)a2 = "sony_arw2_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::sony_arq_load_raw )
  {
    *((_DWORD *)a2 + 2) = 13312;
    *(_QWORD *)a2 = "sony_arq_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::samsung_load_raw )
  {
    *((_DWORD *)a2 + 2) = 65600;
    *(_QWORD *)a2 = "samsung_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::samsung2_load_raw )
  {
    *(_QWORD *)a2 = "samsung2_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::samsung3_load_raw )
  {
    *(_QWORD *)a2 = "samsung3_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::smal_v6_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "smal_v6_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::smal_v9_load_raw )
  {
    *((_DWORD *)a2 + 2) = 256;
    *(_QWORD *)a2 = "smal_v9_load_raw()";
    return 0;
  }
  else if ( (char *)v3 == (char *)guard_check_icall_nop )
  {
    *((_DWORD *)a2 + 2) = 1408;
    *(_QWORD *)a2 = "x3f_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::pentax_4shot_load_raw )
  {
    *((_DWORD *)a2 + 2) = 128;
    *(_QWORD *)a2 = "pentax_4shot_load_raw()";
    return 0;
  }
  else if ( (char *)v3 == (char *)LibRaw::vc5_dng_load_raw_placeholder )
  {
    *((_DWORD *)a2 + 2) = 128;
    *(_QWORD *)a2 = "deflate_dng_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::uncompressed_fp_dng_load_raw )
  {
    *((_DWORD *)a2 + 2) = 128;
    *(_QWORD *)a2 = "uncompressed_fp_dng_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_load_striped_packed_raw )
  {
    *(_QWORD *)a2 = "nikon_load_striped_packed_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_load_padded_packed_raw )
  {
    *(_QWORD *)a2 = "nikon_load_padded_packed_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::nikon_14bit_load_raw )
  {
    *(_QWORD *)a2 = "nikon_14bit_load_raw()";
    return 0;
  }
  else if ( v3 == LibRaw::unpacked_load_raw_fuji_f700s20 )
  {
    *(_QWORD *)a2 = "unpacked_load_raw_fuji_f700s20()";
    return 0;
  }
  else
  {
    if ( v3 == LibRaw::unpacked_load_raw_FujiDBP )
    {
      *(_QWORD *)a2 = "unpacked_load_raw_FujiDBP()";
    }
    else
    {
      *((_DWORD *)a2 + 2) = 0x8000;
      *(_QWORD *)a2 = "Unknown unpack function";
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000df80  test    rdx, rdx
0x18000df83  jnz     short loc_18000DF8B
0x18000df85  mov     eax, 0FFFFFFFFh
0x18000df8a  retn
0x18000df8b  xor     eax, eax
0x18000df8d  mov     [rdx], rax
0x18000df90  mov     [rdx+8], eax
0x18000df93  mov     rax, [rcx+0BB4D0h]
0x18000df9a  test    rax, rax
0x18000df9d  jnz     short loc_18000DFA5
0x18000df9f  mov     eax, 0FFFFFFFCh
0x18000dfa4  retn
0x18000dfa5  lea     rcx, ?android_tight_load_raw@LibRaw@@IEAAXXZ; LibRaw::android_tight_load_raw(void)
0x18000dfac  cmp     rax, rcx
0x18000dfaf  jnz     short loc_18000DFC5
0x18000dfb1  lea     rax, aAndroidTightLo; "android_tight_load_raw()"
0x18000dfb8  mov     dword ptr [rdx+8], 100h
0x18000dfbf  mov     [rdx], rax
0x18000dfc2  xor     eax, eax
0x18000dfc4  retn
0x18000dfc5  lea     rcx, ?android_loose_load_raw@LibRaw@@IEAAXXZ; LibRaw::android_loose_load_raw(void)
0x18000dfcc  cmp     rax, rcx
0x18000dfcf  jnz     short loc_18000DFE5
0x18000dfd1  lea     rax, aAndroidLooseLo; "android_loose_load_raw()"
0x18000dfd8  mov     dword ptr [rdx+8], 100h
0x18000dfdf  mov     [rdx], rax
0x18000dfe2  xor     eax, eax
0x18000dfe4  retn
0x18000dfe5  lea     rcx, ?vc5_dng_load_raw_placeholder@LibRaw@@IEAAXXZ; LibRaw::vc5_dng_load_raw_placeholder(void)
0x18000dfec  cmp     rax, rcx
0x18000dfef  jnz     short loc_18000E005
0x18000dff1  lea     rax, aVc5DngLoadRawP; "vc5_dng_load_raw_placeholder()"
0x18000dff8  mov     dword ptr [rdx+8], 4000h
0x18000dfff  mov     [rdx], rax
0x18000e002  xor     eax, eax
0x18000e004  retn
0x18000e005  lea     rcx, ?canon_600_load_raw@LibRaw@@IEAAXXZ; LibRaw::canon_600_load_raw(void)
0x18000e00c  cmp     rax, rcx
0x18000e00f  jnz     short loc_18000E025
0x18000e011  lea     rax, aCanon600LoadRa; "canon_600_load_raw()"
0x18000e018  mov     dword ptr [rdx+8], 100h
0x18000e01f  mov     [rdx], rax
0x18000e022  xor     eax, eax
0x18000e024  retn
0x18000e025  lea     rcx, ?fuji_compressed_load_raw@LibRaw@@IEAAXXZ; LibRaw::fuji_compressed_load_raw(void)
0x18000e02c  cmp     rax, rcx
0x18000e02f  jnz     short loc_18000E03E
0x18000e031  lea     rax, aFujiCompressed; "fuji_compressed_load_raw()"
0x18000e038  mov     [rdx], rax
0x18000e03b  xor     eax, eax
0x18000e03d  retn
0x18000e03e  lea     rcx, ?fuji_14bit_load_raw@LibRaw@@IEAAXXZ; LibRaw::fuji_14bit_load_raw(void)
0x18000e045  cmp     rax, rcx
0x18000e048  jnz     short loc_18000E057
0x18000e04a  lea     rax, aFuji14bitLoadR; "fuji_14bit_load_raw()"
0x18000e051  mov     [rdx], rax
0x18000e054  xor     eax, eax
0x18000e056  retn
0x18000e057  lea     rcx, ?canon_load_raw@LibRaw@@IEAAXXZ; LibRaw::canon_load_raw(void)
0x18000e05e  cmp     rax, rcx
0x18000e061  jnz     short loc_18000E070
0x18000e063  lea     rax, aCanonLoadRaw; "canon_load_raw()"
0x18000e06a  mov     [rdx], rax
0x18000e06d  xor     eax, eax
0x18000e06f  retn
0x18000e070  lea     rcx, ?lossless_jpeg_load_raw@LibRaw@@IEAAXXZ; LibRaw::lossless_jpeg_load_raw(void)
0x18000e077  cmp     rax, rcx
0x18000e07a  jnz     short loc_18000E090
0x18000e07c  lea     rax, aLosslessJpegLo; "lossless_jpeg_load_raw()"
0x18000e083  mov     dword ptr [rdx+8], 10050h
0x18000e08a  mov     [rdx], rax
0x18000e08d  xor     eax, eax
0x18000e08f  retn
0x18000e090  lea     rcx, ?canon_sraw_load_raw@LibRaw@@IEAAXXZ; LibRaw::canon_sraw_load_raw(void)
0x18000e097  cmp     rax, rcx
0x18000e09a  jnz     short loc_18000E0B0
0x18000e09c  lea     rax, aCanonSrawLoadR; "canon_sraw_load_raw()"
0x18000e0a3  mov     dword ptr [rdx+8], 10000h
0x18000e0aa  mov     [rdx], rax
0x18000e0ad  xor     eax, eax
0x18000e0af  retn
0x18000e0b0  lea     rcx, ?crxLoadRaw@LibRaw@@IEAAXXZ; LibRaw::crxLoadRaw(void)
0x18000e0b7  cmp     rax, rcx
0x18000e0ba  jnz     short loc_18000E0C9
0x18000e0bc  lea     rax, aCrxloadraw; "crxLoadRaw()"
0x18000e0c3  mov     [rdx], rax
0x18000e0c6  xor     eax, eax
0x18000e0c8  retn
0x18000e0c9  lea     rcx, ?lossless_dng_load_raw@LibRaw@@IEAAXXZ; LibRaw::lossless_dng_load_raw(void)
0x18000e0d0  cmp     rax, rcx
0x18000e0d3  jnz     short loc_18000E0E9
0x18000e0d5  lea     rax, aLosslessDngLoa; "lossless_dng_load_raw()"
0x18000e0dc  mov     dword ptr [rdx+8], 10250h
0x18000e0e3  mov     [rdx], rax
0x18000e0e6  xor     eax, eax
0x18000e0e8  retn
0x18000e0e9  lea     rcx, ?packed_dng_load_raw@LibRaw@@IEAAXXZ; LibRaw::packed_dng_load_raw(void)
0x18000e0f0  cmp     rax, rcx
0x18000e0f3  jnz     short loc_18000E109
0x18000e0f5  lea     rax, aPackedDngLoadR; "packed_dng_load_raw()"
0x18000e0fc  mov     dword ptr [rdx+8], 10250h
0x18000e103  mov     [rdx], rax
0x18000e106  xor     eax, eax
0x18000e108  retn
0x18000e109  lea     rcx, ?pentax_load_raw@LibRaw@@IEAAXXZ; LibRaw::pentax_load_raw(void)
0x18000e110  cmp     rax, rcx
0x18000e113  jnz     short loc_18000E129
0x18000e115  lea     rax, aPentaxLoadRaw; "pentax_load_raw()"
0x18000e11c  mov     dword ptr [rdx+8], 10040h
0x18000e123  mov     [rdx], rax
0x18000e126  xor     eax, eax
0x18000e128  retn
0x18000e129  lea     rcx, ?nikon_load_raw@LibRaw@@IEAAXXZ; LibRaw::nikon_load_raw(void)
0x18000e130  cmp     rax, rcx
0x18000e133  jnz     short loc_18000E149
0x18000e135  lea     rax, aNikonLoadRaw; "nikon_load_raw()"
0x18000e13c  mov     dword ptr [rdx+8], 10050h
0x18000e143  mov     [rdx], rax
0x18000e146  xor     eax, eax
0x18000e148  retn
0x18000e149  lea     rcx, ?nikon_coolscan_load_raw@LibRaw@@IEAAXXZ; LibRaw::nikon_coolscan_load_raw(void)
0x18000e150  cmp     rax, rcx
0x18000e153  jnz     short loc_18000E169
0x18000e155  lea     rax, aNikonCoolscanL; "nikon_coolscan_load_raw()"
0x18000e15c  mov     dword ptr [rdx+8], 100h
0x18000e163  mov     [rdx], rax
0x18000e166  xor     eax, eax
0x18000e168  retn
0x18000e169  lea     rcx, ?nikon_he_load_raw_placeholder@LibRaw@@IEAAXXZ; LibRaw::nikon_he_load_raw_placeholder(void)
0x18000e170  cmp     rax, rcx
0x18000e173  jnz     short loc_18000E189
0x18000e175  lea     rax, aNikonHeLoadRaw; "nikon_he_load_raw_placeholder()"
0x18000e17c  mov     dword ptr [rdx+8], 4000h
0x18000e183  mov     [rdx], rax
0x18000e186  xor     eax, eax
0x18000e188  retn
0x18000e189  lea     rcx, ?nikon_load_sraw@LibRaw@@IEAAXXZ; LibRaw::nikon_load_sraw(void)
0x18000e190  cmp     rax, rcx
0x18000e193  jnz     short loc_18000E1A9
0x18000e195  lea     rax, aNikonLoadSraw; "nikon_load_sraw()"
0x18000e19c  mov     dword ptr [rdx+8], 110h
0x18000e1a3  mov     [rdx], rax
0x18000e1a6  xor     eax, eax
0x18000e1a8  retn
0x18000e1a9  lea     rcx, ?nikon_yuv_load_raw@LibRaw@@IEAAXXZ; LibRaw::nikon_yuv_load_raw(void)
0x18000e1b0  cmp     rax, rcx
0x18000e1b3  jnz     short loc_18000E1C9
0x18000e1b5  lea     rax, aNikonLoadYuvLo; "nikon_load_yuv_load_raw()"
0x18000e1bc  mov     dword ptr [rdx+8], 110h
0x18000e1c3  mov     [rdx], rax
0x18000e1c6  xor     eax, eax
0x18000e1c8  retn
0x18000e1c9  lea     rcx, ?rollei_load_raw@LibRaw@@IEAAXXZ; LibRaw::rollei_load_raw(void)
0x18000e1d0  cmp     rax, rcx
0x18000e1d3  jnz     short loc_18000E1E9
0x18000e1d5  lea     rax, aRolleiLoadRaw; "rollei_load_raw()"
0x18000e1dc  mov     dword ptr [rdx+8], 100h
0x18000e1e3  mov     [rdx], rax
0x18000e1e6  xor     eax, eax
0x18000e1e8  retn
0x18000e1e9  lea     rcx, ?phase_one_load_raw@LibRaw@@IEAAXXZ; LibRaw::phase_one_load_raw(void)
0x18000e1f0  cmp     rax, rcx
0x18000e1f3  jnz     short loc_18000E202
0x18000e1f5  lea     rax, aPhaseOneLoadRa_1; "phase_one_load_raw()"
0x18000e1fc  mov     [rdx], rax
0x18000e1ff  xor     eax, eax
0x18000e201  retn
0x18000e202  lea     rcx, ?phase_one_load_raw_c@LibRaw@@IEAAXXZ; LibRaw::phase_one_load_raw_c(void)
0x18000e209  cmp     rax, rcx
0x18000e20c  jnz     short loc_18000E222
0x18000e20e  lea     rax, aPhaseOneLoadRa_0; "phase_one_load_raw_c()"
0x18000e215  mov     dword ptr [rdx+8], 10000h
0x18000e21c  mov     [rdx], rax
0x18000e21f  xor     eax, eax
0x18000e221  retn
0x18000e222  lea     rcx, ?phase_one_load_raw_s@LibRaw@@IEAAXXZ; LibRaw::phase_one_load_raw_s(void)
0x18000e229  cmp     rax, rcx
0x18000e22c  jnz     short loc_18000E23B
0x18000e22e  lea     rax, aPhaseOneLoadRa; "phase_one_load_raw_s()"
0x18000e235  mov     [rdx], rax
0x18000e238  xor     eax, eax
0x18000e23a  retn
0x18000e23b  lea     rcx, ?hasselblad_load_raw@LibRaw@@IEAAXXZ; LibRaw::hasselblad_load_raw(void)
0x18000e242  cmp     rax, rcx
0x18000e245  jnz     short loc_18000E25B
0x18000e247  lea     rax, aHasselbladLoad; "hasselblad_load_raw()"
0x18000e24e  mov     dword ptr [rdx+8], 10000h
0x18000e255  mov     [rdx], rax
0x18000e258  xor     eax, eax
0x18000e25a  retn
0x18000e25b  lea     rcx, ?leaf_hdr_load_raw@LibRaw@@IEAAXXZ; LibRaw::leaf_hdr_load_raw(void)
0x18000e262  cmp     rax, rcx
0x18000e265  jnz     short loc_18000E274
0x18000e267  lea     rax, aLeafHdrLoadRaw; "leaf_hdr_load_raw()"
0x18000e26e  mov     [rdx], rax
0x18000e271  xor     eax, eax
0x18000e273  retn
0x18000e274  lea     rcx, ?unpacked_load_raw@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw(void)
0x18000e27b  cmp     rax, rcx
0x18000e27e  jnz     short loc_18000E294
0x18000e280  lea     rax, aUnpackedLoadRa; "unpacked_load_raw()"
0x18000e287  mov     dword ptr [rdx+8], 1000h
0x18000e28e  mov     [rdx], rax
0x18000e291  xor     eax, eax
0x18000e293  retn
0x18000e294  lea     rcx, ?unpacked_load_raw_reversed@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw_reversed(void)
0x18000e29b  cmp     rax, rcx
0x18000e29e  jnz     short loc_18000E2B4
0x18000e2a0  lea     rax, aUnpackedLoadRa_2; "unpacked_load_raw_reversed()"
0x18000e2a7  mov     dword ptr [rdx+8], 100h
0x18000e2ae  mov     [rdx], rax
0x18000e2b1  xor     eax, eax
0x18000e2b3  retn
0x18000e2b4  lea     rcx, ?sinar_4shot_load_raw@LibRaw@@IEAAXXZ; LibRaw::sinar_4shot_load_raw(void)
0x18000e2bb  cmp     rax, rcx
0x18000e2be  jnz     short loc_18000E2D4
0x18000e2c0  lea     rax, aSinar4shotLoad; "sinar_4shot_load_raw()"
0x18000e2c7  mov     dword ptr [rdx+8], 800h
0x18000e2ce  mov     [rdx], rax
0x18000e2d1  xor     eax, eax
0x18000e2d3  retn
0x18000e2d4  lea     rcx, ?imacon_full_load_raw@LibRaw@@IEAAXXZ; LibRaw::imacon_full_load_raw(void)
0x18000e2db  cmp     rax, rcx
0x18000e2de  jnz     short loc_18000E2ED
0x18000e2e0  lea     rax, aImaconFullLoad; "imacon_full_load_raw()"
0x18000e2e7  mov     [rdx], rax
0x18000e2ea  xor     eax, eax
0x18000e2ec  retn
0x18000e2ed  lea     rcx, ?hasselblad_full_load_raw@LibRaw@@IEAAXXZ; LibRaw::hasselblad_full_load_raw(void)
0x18000e2f4  cmp     rax, rcx
0x18000e2f7  jnz     short loc_18000E306
0x18000e2f9  lea     rax, aHasselbladFull; "hasselblad_full_load_raw()"
0x18000e300  mov     [rdx], rax
0x18000e303  xor     eax, eax
0x18000e305  retn
0x18000e306  lea     rcx, ?packed_load_raw@LibRaw@@IEAAXXZ; LibRaw::packed_load_raw(void)
0x18000e30d  cmp     rax, rcx
0x18000e310  jnz     short loc_18000E326
0x18000e312  lea     rax, aPackedLoadRaw; "packed_load_raw()"
0x18000e319  mov     dword ptr [rdx+8], 10040h
0x18000e320  mov     [rdx], rax
0x18000e323  xor     eax, eax
0x18000e325  retn
0x18000e326  lea     rcx, ?broadcom_load_raw@LibRaw@@IEAAXXZ; LibRaw::broadcom_load_raw(void)
0x18000e32d  cmp     rax, rcx
0x18000e330  jnz     short loc_18000E346
0x18000e332  lea     rax, aBroadcomLoadRa; "broadcom_load_raw()"
0x18000e339  mov     dword ptr [rdx+8], 100h
0x18000e340  mov     [rdx], rax
0x18000e343  xor     eax, eax
0x18000e345  retn
0x18000e346  lea     rcx, ?nokia_load_raw@LibRaw@@IEAAXXZ; LibRaw::nokia_load_raw(void)
0x18000e34d  cmp     rax, rcx
0x18000e350  jnz     short loc_18000E366
0x18000e352  lea     rax, aNokiaLoadRaw; "nokia_load_raw()"
0x18000e359  mov     dword ptr [rdx+8], 100h
0x18000e360  mov     [rdx], rax
0x18000e363  xor     eax, eax
0x18000e365  retn
0x18000e366  lea     rcx, ?panasonic_load_raw@LibRaw@@IEAAXXZ; LibRaw::panasonic_load_raw(void)
0x18000e36d  cmp     rax, rcx
0x18000e370  jnz     short loc_18000E386
0x18000e372  lea     rax, aPanasonicLoadR; "panasonic_load_raw()"
0x18000e379  mov     dword ptr [rdx+8], 40h ; '@'
0x18000e380  mov     [rdx], rax
0x18000e383  xor     eax, eax
0x18000e385  retn
0x18000e386  lea     rcx, ?panasonicC6_load_raw@LibRaw@@IEAAXXZ; LibRaw::panasonicC6_load_raw(void)
0x18000e38d  cmp     rax, rcx
0x18000e390  jnz     short loc_18000E39F
0x18000e392  lea     rax, aPanasonicc6Loa; "panasonicC6_load_raw()"
0x18000e399  mov     [rdx], rax
0x18000e39c  xor     eax, eax
0x18000e39e  retn
0x18000e39f  lea     rcx, ?panasonicC7_load_raw@LibRaw@@IEAAXXZ; LibRaw::panasonicC7_load_raw(void)
0x18000e3a6  cmp     rax, rcx
0x18000e3a9  jnz     short loc_18000E3B8
0x18000e3ab  lea     rax, aPanasonicc7Loa; "panasonicC7_load_raw()"
0x18000e3b2  mov     [rdx], rax
0x18000e3b5  xor     eax, eax
0x18000e3b7  retn
0x18000e3b8  lea     rcx, ?olympus_load_raw@LibRaw@@IEAAXXZ; LibRaw::olympus_load_raw(void)
0x18000e3bf  cmp     rax, rcx
0x18000e3c2  jnz     short loc_18000E3D8
0x18000e3c4  lea     rax, aOlympusLoadRaw; "olympus_load_raw()"
0x18000e3cb  mov     dword ptr [rdx+8], 10040h
0x18000e3d2  mov     [rdx], rax
0x18000e3d5  xor     eax, eax
0x18000e3d7  retn
0x18000e3d8  lea     rcx, ?minolta_rd175_load_raw@LibRaw@@IEAAXXZ; LibRaw::minolta_rd175_load_raw(void)
0x18000e3df  cmp     rax, rcx
0x18000e3e2  jnz     short loc_18000E3F1
0x18000e3e4  lea     rax, aMinoltaRd175Lo; "minolta_rd175_load_raw()"
0x18000e3eb  mov     [rdx], rax
0x18000e3ee  xor     eax, eax
0x18000e3f0  retn
0x18000e3f1  lea     rcx, ?quicktake_100_load_raw@LibRaw@@IEAAXXZ; LibRaw::quicktake_100_load_raw(void)
0x18000e3f8  cmp     rax, rcx
0x18000e3fb  jnz     short loc_18000E40A
0x18000e3fd  lea     rax, aQuicktake100Lo; "quicktake_100_load_raw()"
  ... truncated ...
```
